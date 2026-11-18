# Baza danych SKW — wstępny model logiczny

**Status:** propozycja logiczna do dalszej walidacji; nie jest migracją SQL ani zatwierdzonym schematem fizycznym. Nazwy tabel są robocze.

## Proponowane encje

| Encja | Główne pola | Kluczowe ograniczenia |
|---|---|---|
| users | id, name, email, password_hash lub external_id, is_active | konto ma identyfikator; dane uwierzytelniania nie mogą być przechowywane jawnie |
| roles | id, code, name | kod roli jest unikatowy |
| user_roles | user_id, role_id | w v1 proponowana jedna podstawowa rola na konto (BR-09) |
| consultation_slots | id, lecturer_id, starts_at, ends_at, capacity, status, location | starts_at < ends_at; capacity >= 1; lecturer_id wskazuje wykładowcę |
| bookings | id, slot_id, student_id, created_at, status | aktywnych zapisów nie może być więcej niż capacity; brak duplikatu aktywnego zapisu |

## Relacje

- users 1:N consultation_slots jako właściciel terminów (wykładowca).
- users 1:N bookings jako student.
- consultation_slots 1:N bookings.
- users N:M roles przez user_roles; wstępne BR-09 ogranicza konto do jednej roli podstawowej.

## Krytyczne ograniczenia integralności

1. Rezerwacja musi sprawdzić dostępność i utworzyć zapis w jednej transakcji.
2. Nie wolno polegać wyłącznie na wcześniejszym odczycie listy wolnych terminów.
3. Należy zabezpieczyć operację przed równoczesnym przekroczeniem limitu (FR-08 / NFR-05).
4. Należy uniemożliwić duplikat aktywnego zapisu (FR-09).
5. Zmiana statusu zapisu powinna być atomowa z aktualizacją widoku dostępności.

## Otwarte decyzje

Silnik bazy i sposób blokowania / izolacji transakcji nie zostały wybrane. Retencja anulowanych zapisów pozostaje pytaniem Q-11. Należy zdecydować, czy utrwalać pełną historię statusów, a także doprecyzować zasady przechowywania danych osobowych i uprawnienia administratora.

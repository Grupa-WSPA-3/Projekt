# P-02 — Zarządzanie terminami konsultacji przez wykładowcę (TO-BE)

**Wersja:** 0.1 — proces pomocniczy  
**Właściciel procesu:** Kostiantyn Kyrylenko  
**Uczestnicy / tory:** Wykładowca, System SKW  
**Cel:** umożliwić wykładowcy utrzymywanie aktualnych terminów i list zapisów w granicach jego uprawnień.

## Zdarzenie początkowe

Wykładowca chce opublikować nowy termin, zmienić termin bez aktywnych zapisów albo odwołać własną konsultację.

## Kroki

| Krok | Tor | Czynność | Typ | Wymagania / reguły |
|---|---|---|---|---|
| P-02.1 | Wykładowca | rozpoczyna zarządzanie własnymi terminami | zadanie użytkownika | FR-02, FR-11, FR-12, FR-14 |
| P-02.2 | System SKW | weryfikuje rolę wykładowcy i właściciela operacji | zadanie usługi | FR-02, BR-04 |
| P-02.3 | Wykładowca | wybiera utworzenie, edycję albo anulowanie terminu | zadanie użytkownika | FR-11, FR-12, FR-14 |
| P-02.4 | Wykładowca | podaje dane nowego terminu lub zakres zmiany | zadanie użytkownika | FR-11, FR-12, BR-01 |
| P-02.5 | System SKW | waliduje początek, koniec, status i właściciela terminu | zadanie usługi | FR-02, FR-11, FR-12, BR-01, BR-04 |
| P-02.6 | System SKW | sprawdza liczbę aktywnych zapisów przed zmianą daty/godziny lub anulowaniem | zadanie usługi | FR-12, FR-14, BR-05, BR-06 |
| P-02.7 | System SKW | zapisuje nowy termin, zmianę albo status anulowania | zadanie usługi | FR-11, FR-12, FR-14 |
| P-02.8 | System SKW | udostępnia zaktualizowany termin / listę zapisów i status operacji | zadanie usługi | FR-13, FR-16, FR-17 |

## Główne decyzje i ścieżki alternatywne

| Bramka | Pytanie | TAK | NIE |
|---|---|---|---|
| G-01 | Czy użytkownik ma rolę wykładowcy i jest właścicielem terminu? | kontynuuj operację | odmów dostępu, bez zmiany danych |
| G-02 | Czy dane terminu są poprawne (data przyszła, koniec po początku)? | zapisz nowy termin / zmianę | pokaż błąd walidacji |
| G-03 | Czy termin ma aktywne zapisy? | przy edycji daty/godziny zablokuj; przy anulowaniu przejdź do aktualizacji statusów | edytuj / anuluj zgodnie z wybraną operacją |

## Wyniki procesu

- nowy termin został utworzony i może być pokazany studentom;
- termin bez aktywnych zapisów został zmieniony;
- termin został anulowany, a zapisy powiązane uzyskały jasny status anulowania terminu;
- operacja została odrzucona z powodu braku uprawnień, niepoprawnych danych lub konfliktu z aktywnymi zapisami.

## Wyjątki

1. Wykładowca próbuje zarządzać terminem należącym do innej osoby — odmowa autoryzacji (FR-02 / BR-04).
2. Data jest przeszła lub koniec nie następuje po początku — odrzucenie walidacji (FR-11 / BR-01).
3. Wykładowca próbuje zmienić datę/godzinę terminu z aktywnymi zapisami — blokada zgodnie z BR-05; alternatywą jest anulowanie i utworzenie nowego terminu.
4. Odwołanie terminu ma aktywne zapisy — system musi zmienić widoczny status powiązanych zapisów (FR-14 / FR-16).

## Założenia i pytania

- Zmiana miejsca / opisu bez zmiany daty i godziny wymaga doprecyzowania: obecny zakres blokady dotyczy daty i godziny.
- Czy można edytować termin, jeżeli ma aktywne zapisy? Q-04.
- Jakie dane terminu są obowiązkowe? Q-13.
- Kto ma prawo wglądu do list zapisów poza właścicielem terminu? Q-06.


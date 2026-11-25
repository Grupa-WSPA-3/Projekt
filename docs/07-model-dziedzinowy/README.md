# Model dziedzinowy SKW — szkic pojęciowy

**Status:** szkic wejściowy wynikający ze słownika 0.3 i wymagań 0.2; nie jest zatwierdzonym modelem klas ani schematem bazy danych.

## Główne pojęcia

| Pojęcie | Znaczenie | Powiązanie |
|---|---|---|
| Konto użytkownika | osoba posiadająca dostęp do systemu | ma jedną podstawową rolę |
| Rola | Student, Wykładowca albo Administrator | określa uprawnienia konta |
| Termin konsultacji | przedział czasu udostępniony przez wykładowcę | ma właściciela, limit miejsc i status |
| Zapis | powiązanie studenta z terminem | ma status Aktywny lub Anulowany |
| Limit miejsc | maksymalna liczba aktywnych zapisów dla terminu | liczba aktywnych zapisów nie może go przekroczyć |

## Relacje pojęciowe

```mermaid
erDiagram
    ACCOUNT ||--|| ROLE : has_primary_role
    ACCOUNT ||--o{ CONSULTATION_SLOT : lecturer_owns
    ACCOUNT ||--o{ BOOKING : student_creates
    CONSULTATION_SLOT ||--o{ BOOKING : contains
    CONSULTATION_SLOT {
        id slot_id
        datetime starts_at
        datetime ends_at
        int capacity
        string status
    }
    BOOKING {
        id booking_id
        datetime created_at
        string status
    }
```

## Zasady dziedzinowe

- Każdy termin ma jednego wykładowcę-właściciela.
- Każdy zapis dotyczy jednego studenta i jednego terminu.
- Aktywny zapis zajmuje jedno miejsce; anulowany zapis go nie zajmuje.
- Liczba aktywnych zapisów nie przekracza limitu terminu.
- Student nie może anulować zapisu innej osoby.

## Do dopracowania

Potwierdzić liczbę ról na konto (Q-05 / BR-09), dostęp administratora do list zapisów (Q-06), retencję danych historycznych (Q-11) oraz statusy i przejścia terminów i zapisów. Pełny model klas należy przygotować na etapie poświęconym temu zagadnieniu.

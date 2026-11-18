# P-02 — Zarządzanie terminami konsultacji przez wykładowcę (TO-BE)

**Wersja:** 0.2 — proces pomocniczy  
**Właściciel procesu:** Kostiantyn Kyrylenko  
**Pula BPMN (opis logiczny):** Uczelnia · **Tory:** Wykładowca, System SKW

## Cel procesu

Umożliwić wykładowcy publikowanie i utrzymywanie własnych terminów oraz przeglądanie list zapisów bez naruszania uprawnień i spójności danych.

## Wyzwalacz i warunki

**Zdarzenie początkowe:** Wykładowca chce utworzyć nowy termin, edytować termin bez aktywnych zapisów, odwołać własny termin albo sprawdzić listę zapisów.

**Warunki wstępne:** wykładowca jest zalogowany; system weryfikuje rolę i własność terminu przy każdej chronionej operacji (FR-01, FR-02, BR-04).

## Kroki procesu i wymagania

| Krok | Tor | Typ zadania | Czynność biznesowa | Wymagania / reguły |
|---|---|---|---|---|
| P-02.1 | Wykładowca | użytkownika | rozpoczyna zarządzanie własnymi terminami | FR-01 |
| P-02.2 | System SKW | usługi | weryfikuje rolę Wykładowca i własność wybranego terminu | FR-02, BR-04 |
| P-02.3 | Wykładowca | użytkownika | wybiera utworzenie, edycję, anulowanie albo przegląd listy zapisów | FR-11, FR-12, FR-13, FR-14 |
| P-02.4 | Wykładowca | użytkownika | podaje dane nowego terminu lub zakres zmian | FR-11, FR-12, BR-01 |
| P-02.5 | System SKW | usługi | waliduje datę, czas, status oraz właściciela terminu | FR-02, FR-11, FR-12, BR-01, BR-04 |
| P-02.6 | System SKW | usługi | sprawdza aktywne zapisy przed edycją daty/godziny albo anulowaniem terminu | FR-12, FR-14, BR-05, BR-06 |
| P-02.7 | System SKW | usługi | zapisuje nowy termin, zmianę bez aktywnych zapisów albo status anulowania i statusy powiązanych zapisów | FR-11, FR-12, FR-14, BR-06 |
| P-02.8 | System SKW | usługi | udostępnia wykładowcy zaktualizowany termin, listę zapisów lub wynik operacji | FR-13, FR-16, FR-17 |

## Bramki i ścieżki alternatywne

| Bramka | Pytanie | TAK | NIE |
|---|---|---|---|
| G-01 | Czy użytkownik ma rolę Wykładowca i jest właścicielem terminu? | kontynuuj | odmów dostępu; dane pozostają bez zmian |
| G-02 | Czy dane terminu są poprawne (start w przyszłości, koniec po początku)? | kontynuuj zapis | pokaż błąd walidacji |
| G-03 | Czy termin ma aktywne zapisy? | przy zmianie daty/godziny zablokuj; anulowanie przeprowadź z aktualizacją statusów | zezwól na edycję / anulowanie zgodnie z operacją |

## Wyniki procesu

- termin został utworzony i może zostać pokazany studentom;
- termin bez aktywnych zapisów został zmieniony;
- termin został anulowany, a powiązane aktywne zapisy mają czytelny status odwołania;
- lista zapisów została pokazana wyłącznie uprawnionemu wykładowcy;
- operacja została odrzucona z powodu braku uprawnień, błędnej daty albo ograniczenia edycji.

## Wyjątki

1. Wykładowca próbuje zarządzać terminem należącym do innej osoby — odmowa autoryzacji (FR-02 / BR-04).
2. Początek terminu jest w przeszłości albo koniec nie następuje po początku — błąd walidacji (FR-11 / BR-01).
3. Wykładowca próbuje zmienić datę/godzinę terminu z aktywnymi zapisami — blokada zgodnie z BR-05; dostępna ścieżka to anulowanie i utworzenie nowego terminu.
4. Odwołany termin ma aktywne zapisy — System SKW aktualizuje powiązane statusy, aby student rozumiał przyczynę zmiany (FR-14 / FR-16).

## Otwarte kwestie

- Edycja terminu z aktywnymi zapisami — Q-04.
- Obowiązkowe dane terminu / miejsce / forma — Q-13 i Q-07.
- Wgląd administratora do list zapisów — Q-06.
- Retencja danych historycznych — Q-11.


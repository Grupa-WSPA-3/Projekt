# Plan testów SKW — wstępny zakres i kryteria

**Status:** plan testów na poziomie wymagań; przypadki testowe i automatyzacja do opracowania w dalszej części projektu. Testy nie zostały jeszcze wykonane.

## Poziomy testów

- **Testy jednostkowe:** reguły walidacji dat, statusów, limitu i uprawnień.
- **Testy integracyjne:** współpraca API z bazą danych podczas zapisu, anulowania i zarządzania terminem.
- **Testy systemowe:** przepływy studenta i wykładowcy od początku do końca.
- **Testy akceptacyjne:** kryteria GWT w historyjkach US-01…US-06.
- **Testy użyteczności i kompatybilności:** kryteria NFR-03, NFR-04 i NFR-08.

## Minimalny katalog scenariuszy

| ID | Scenariusz | Powiązanie |
|---|---|---|
| TC-01 | poprawne i niepoprawne logowanie | FR-01, US-01 |
| TC-02 | dostęp zgodnie z rolą; odmowa dla obcej roli | FR-02, NFR-06 |
| TC-03 | lista nie pokazuje terminów przeszłych, anulowanych ani pełnych | FR-03, P-01 |
| TC-04 | filtrowanie po wykładowcy i zakresie dat | FR-04, FR-05 |
| TC-05 | poprawny zapis na wolny termin | FR-07, US-03 |
| TC-06 | dwie równoczesne próby ostatniego miejsca — najwyżej jedna udana | FR-08, NFR-05, BR-02 |
| TC-07 | brak duplikatu aktywnego zapisu | FR-09, BR-03 |
| TC-08 | anulowanie własnego zapisu i zwolnienie miejsca | FR-10, P-03 |
| TC-09 | odmowa anulowania zapisu innej osoby | FR-02, FR-10, BR-04 |
| TC-10 | utworzenie terminu i odrzucenie błędnej daty | FR-11, BR-01 |
| TC-11 | blokada edycji terminu z aktywnymi zapisami | FR-12, BR-05, Q-04 |
| TC-12 | wykładowca widzi listę własnego terminu | FR-13, BR-08 |
| TC-13 | odwołanie terminu i aktualizacja statusów zapisów | FR-14, FR-16, BR-06 |
| TC-14 | administrator aktywuje konto i przypisuje rolę | FR-15 |
| TC-15 | komunikaty sukcesu i odmowy są jednoznaczne | FR-17, FR-18 |

## Warunki odbioru

- Każde FR ma przynajmniej jeden scenariusz testowy.
- Każda reguła BR ma co najmniej jeden test.
- Wszystkie scenariusze Must przechodzą przed uznaniem wersji za gotową.
- Wyniki testów zapisujemy z datą, środowiskiem, wersją i dowodem wykonania.
- Wartości NFR-02 i NFR-04 muszą zostać zmierzone, a nie tylko zadeklarowane.

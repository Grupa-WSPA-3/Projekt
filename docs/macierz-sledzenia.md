# Macierz śledzenia wymagań — SKW

**Wersja:** 0.3 — macierz po walkthrough procesów na etapie 5  
**Zakres:** potrzeba → wymaganie → historyjka → priorytet MoSCoW → proces / krok.

Kody potrzeb N-xx, FR-xx, NFR-xx, BR-xx, US-xx oraz P-xx są spójne z `docs/03-wymagania.md` i `docs/04-procesy/`.

## 1. Macierz wymagań funkcjonalnych

| Potrzeba | Wymaganie | Historyjka | MoSCoW | Proces |
|---|---|---|---|---|
| N-09 | FR-01 — logowanie aktywnego konta | US-01 | Must | warunek wejściowy P-01, P-02 i P-03: użytkownik jest zalogowany |
| N-09 | FR-02 — dostęp zgodny z rolą | US-01 | Must | kontrola uprawnień w P-01.5–P-01.10, P-02.2, P-03.2 |
| N-01, N-04 | FR-03 — lista przyszłych dostępnych terminów | US-02 | Must | P-01.1, P-01.3 |
| N-02 | FR-04 — filtrowanie po wykładowcy | US-02 | Should | P-01.2–P-01.3 |
| N-02 | FR-05 — filtrowanie po dacie | US-02 | Should | P-01.2–P-01.3 |
| N-03 | FR-06 — szczegóły terminu | US-02 | Should | P-01.4 |
| N-04 | FR-07 — zapis studenta na termin | US-03 | Must | P-01.5, P-01.9 |
| N-04 | FR-08 — atomowa kontrola limitu w chwili zatwierdzania | US-03 | Must | P-01.8 |
| N-04 | FR-09 — brak duplikatu aktywnego zapisu | US-03 | Must | P-01.7, P-01.12 |
| N-05 | FR-10 — anulowanie własnego zapisu | US-04 | Must | P-03.1–P-03.6 |
| N-06 | FR-11 — utworzenie terminu przez wykładowcę | US-05 | Must | P-02.3–P-02.7 |
| N-06 | FR-12 — edycja własnego terminu bez aktywnych zapisów | US-05 | Should | P-02.3–P-02.7 |
| N-07, N-09 | FR-13 — lista zapisów dla własnego terminu | US-06 | Should | P-02.3, P-02.8 |
| N-06, N-10 | FR-14 — anulowanie własnego terminu i aktualizacja zapisów | US-05 | Must | P-02.3, P-02.6–P-02.8 |
| N-08 | FR-15 — administracja kontami i rolami | US-07 | Should | — (osobny proces administracyjny nie jest częścią P-01…P-03) |
| N-10 | FR-16 — status własnego zapisu / odwołanego terminu | US-04, US-05 | Should | P-01.10, P-02.8, P-03.6 |
| N-10 | FR-17 — komunikat o wyniku operacji zapisu | US-03, US-04 | Must | P-01.10–P-01.13, P-03.6 |
| N-04, N-10 | FR-18 — odmowa zapisu na termin niedostępny | US-03 | Should | P-01.6, P-01.8, P-01.11, P-01.13 |

**Uwaga dotycząca pustego procesu:** FR-15 jest funkcją administratora i nie mieści się w trzech wybranych przepływach studenta / wykładowcy. Jawnie oznaczono „—” zamiast pozorować powiązanie. Proces administracyjny może zostać dodany, gdy będzie wymagany na kolejnym etapie.

## 2. Śledzenie wymagań niefunkcjonalnych

| ID | Kategoria ISO/IEC 25010:2023 | Powiązane potrzeby / wymagania | Proces / miejsce weryfikacji |
|---|---|---|---|
| NFR-01 | Przydatność funkcjonalna (*functional suitability*) | wszystkie historyjki Must | odbiór kryteriów US-01…US-05 i powiązanych FR |
| NFR-02 | Efektywność działania (*performance efficiency*) | N-01, N-02; FR-03…FR-06 | P-01.1–P-01.3; test obciążeniowy |
| NFR-03 | Kompatybilność (*compatibility*) | N-01, N-04 | przeglądanie / zapis w obsługiwanych przeglądarkach; P-01 |
| NFR-04 | Zdolność interakcji (*interaction capability*) | N-04, N-10 | P-01.1–P-01.10; test użyteczności |
| NFR-05 | Niezawodność (*reliability*) | N-04; FR-08 | P-01.8–P-01.9; test współbieżności |
| NFR-06 | Bezpieczeństwo (*security*) | N-09; FR-01, FR-02, FR-10, FR-13, FR-15 | kontrola dostępu w P-01, P-02.2, P-03.2; testy negatywne |
| NFR-07 | Utrzymywalność (*maintainability*) | N-04, N-05, N-06; BR-01…BR-10 | mapowanie BR → test; P-01…P-03 |
| NFR-08 | Elastyczność (*flexibility*) | N-01, N-04 | widoki P-01 i P-03; test responsywności 360 / 768 / 1366 px |

Charakterystyka Safety została omówiona w wymaganiach i uznana za nieadekwatną do obecnego zakresu SKW; nie ma dla niej osobnego NFR. Decyzja wymaga ponownej oceny, jeśli zakres zostanie rozszerzony.

## 3. Śledzenie reguł biznesowych

| Reguła | Proces / krok | Wymagania |
|---|---|---|
| BR-01 — poprawny zakres dat i termin w przyszłości | P-02.5; P-01.6 | FR-11, FR-12, FR-18 |
| BR-02 — limit aktywnych zapisów | P-01.3, P-01.8, P-01.9 | FR-03, FR-07, FR-08, FR-18 |
| BR-03 — brak duplikatu aktywnego zapisu | P-01.7 | FR-09 |
| BR-04 — operacje tylko na własnym zasobie / zgodnie z rolą | P-02.2, P-03.2 oraz kontrola autoryzacji w P-01 | FR-02, FR-10, FR-12, FR-13, FR-14, FR-15 |
| BR-05 — blokada edycji obsadzonego terminu | P-02.6–P-02.7 | FR-12, FR-14 |
| BR-06 — anulowany termin nie jest dostępny, a powiązane zapisy mają status | P-01.3, P-02.7–P-02.8 | FR-03, FR-14, FR-16, FR-18 |
| BR-07 — anulowany zapis zwalnia miejsce | P-01.9, P-03.6 | FR-08, FR-10 |
| BR-08 — ograniczenie widoczności listy zapisów | P-02.2, P-02.8 | FR-02, FR-13 |
| BR-09 — jedna podstawowa rola konta | warunek wejściowy P-01…P-03 / model kont | FR-01, FR-02, FR-15 |
| BR-10 — termin musi być aktywny, przyszły i dostępny w chwili rezerwacji | P-01.6–P-01.8 | FR-03, FR-07, FR-08, FR-18 |

## 4. Zmiany wprowadzone po walkthrough

- **FR-08** doprecyzowano o atomową kontrolę dostępności w chwili zatwierdzania zapisu — P-01.8.
- **FR-14** doprecyzowano o zmianę statusów zapisów powiązanych z anulowanym terminem — P-02.6–P-02.8.
- Dodano **BR-10**, która łączy walidację terminu i ponowną kontrolę dostępności — P-01.6–P-01.8.
- **FR-18** pozostaje Should, ponieważ część walidacji jest współdzielona z FR-03 i FR-08; scenariusze negatywne nadal są opisane w US-03.

## 5. Kontrola kompletności

- Każde FR-01…FR-18 ma potrzeby źródłowe oraz historyjkę.
- Każde FR ma krok procesu, warunek wejściowy albo jawne wyjaśnienie „—”.
- Wszystkie wymagania Must mają sprawdzalne kryteria GWT w historyjkach.
- Każdy FR Must jest powiązany z krokiem procesu albo jawnie opisanym warunkiem.
- Każda BR ma co najmniej jeden proces / krok, w którym jest egzekwowana.
- Zmiana identyfikatora, priorytetu lub kroku procesu wymaga aktualizacji wymagań, procesu i tej macierzy w tym samym PR.


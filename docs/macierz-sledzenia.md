# Macierz śledzenia wymagań — SKW

**Wersja:** 0.2 — zawiera powiązanie z procesami P-00…P-03 po walkthrough etapu 5.

Macierz łączy potrzebę, wymaganie, historyjkę, priorytet i krok procesu. Kreska w kolumnie „Proces” oznacza, że funkcja administracyjna nie należy do trzech modelowanych przepływów operacyjnych lub wymaga osobnego procesu.

| Potrzeba | Wymaganie | Historyjka | Priorytet | Proces / krok |
|---|---|---|---|---|
| N-09 | FR-01 | US-01 | Must | P-01.1, P-02.1, P-03.1 — sesja użytkownika |
| N-09 | FR-02 | US-01, US-06 | Must | P-01.1, P-02.2, P-03.2 |
| N-01 | FR-03 | US-02 | Must | P-01.1–P-01.3 |
| N-02 | FR-04 | US-02 | Should | P-01.2–P-01.3 |
| N-02 | FR-05 | US-02 | Should | P-01.2–P-01.3 |
| N-03 | FR-06 | US-02 | Should | P-01.4 |
| N-04 | FR-07 | US-03 | Must | P-01.5, P-01.9 |
| N-04 | FR-08 | US-03 | Must | P-01.8 |
| N-04 | FR-09 | US-03 | Must | P-01.7 |
| N-05 | FR-10 | US-04 | Must | P-03.1–P-03.6 |
| N-06 | FR-11 | US-05 | Must | P-02.1–P-02.5, P-02.7 |
| N-06 | FR-12 | US-05 | Should | P-02.3–P-02.6 |
| N-07 | FR-13 | US-06 | Should | P-02.8 |
| N-06, N-10 | FR-14 | US-05 | Must | P-02.3, P-02.6–P-02.8 |
| N-08 | FR-15 | US-06 | Should | — osobny proces administracyjny poza P-01…P-03 |
| N-10 | FR-16 | US-04, US-05, US-06 | Should | P-01.10, P-02.8, P-03.6 |
| N-10 | FR-17 | US-03, US-04 | Must | P-01.10–P-01.11, P-03.6 |
| N-04, N-10 | FR-18 | US-03 | Must | P-01.6, P-01.8, P-01.11 |

## Śledzenie NFR

| NFR | Obszar | Powiązane wymagania / procesy | Weryfikacja |
|---|---|---|---|
| NFR-01 | kompletność funkcjonalna | wszystkie FR / P-01…P-03 | wszystkie kryteria US wykonane |
| NFR-02 | wydajność | FR-03…FR-06 / P-01 | test obciążeniowy wyszukiwania |
| NFR-03 | kompatybilność | FR-03…FR-17 / widoki P-01…P-03 | macierz przeglądarek |
| NFR-04 | użyteczność | FR-03…FR-10 / P-01, P-03 | test użyteczności z pomiarem czasu |
| NFR-05 | niezawodność | FR-08, FR-09 / P-01.7–P-01.9 | test współbieżności i limitów |
| NFR-06 | bezpieczeństwo | FR-01, FR-02, FR-10, FR-13, FR-15 / P-01…P-03 | testy negatywne ról |
| NFR-07 | utrzymywalność | BR-01…BR-10 / P-01…P-03 | każda reguła ma test |
| NFR-08 | responsywność | widoki FR-03…FR-17 / P-01…P-03 | kontrola szerokości 360, 768 i 1366 px |

## Zmiany po walkthrough

- **FR-08** doprecyzowano o atomowe sprawdzenie dostępności w chwili zatwierdzania — krok P-01.8.
- **FR-14** doprecyzowano o status powiązanych zapisów po anulowaniu terminu — kroki P-02.6–P-02.8.
- Dodano **BR-10**: rezerwacja wymaga, aby termin był aktywny, przyszły i dostępny w chwili zatwierdzenia — P-01.6–P-01.8.

Zmiany są ujęte w PR, wymagają przeglądu zespołu. Jeśli macierz lub wymagania zostaną zmienione, należy zaktualizować obie strony powiązania.


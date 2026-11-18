# Macierz śledzenia — potrzeby i wymagania

**Wersja:** 0.1 — robocza

Macierz łączy potrzeby N-xx z wstępnymi wymaganiami funkcjonalnymi i niefunkcjonalnymi. Większość źródeł opiera się obecnie na karcie projektu i założeniach zespołu. Po wywiadzie należy zweryfikować każde powiązanie i poprawić je razem z dokumentem wymagań.

| Potrzeba | Powiązane wymagania funkcjonalne | Powiązane wymagania niefunkcjonalne |
|---|---|---|
| N-01 — aktualne terminy w jednym miejscu | FR-03 | NFR-02, NFR-03, NFR-08 |
| N-02 — wyszukiwanie według wykładowcy i terminu | FR-04, FR-05 | NFR-02, NFR-03 |
| N-03 — informacje potrzebne do wyboru terminu | FR-06 | NFR-04, NFR-08 |
| N-04 — zapis bez przekroczenia limitu | FR-03, FR-07, FR-08, FR-09, FR-18 | NFR-02, NFR-05 |
| N-05 — anulowanie własnego zapisu | FR-10 | NFR-04, NFR-06 |
| N-06 — samodzielne zarządzanie terminami przez wykładowcę | FR-11, FR-12, FR-14 | NFR-05, NFR-07 |
| N-07 — lista studentów zapisanych na termin | FR-13 | NFR-06 |
| N-08 — zarządzanie kontami i rolami | FR-15 | NFR-06 |
| N-09 — dostęp zgodny z rolą | FR-01, FR-02, FR-13, FR-15 | NFR-06 |
| N-10 — czytelny wynik operacji | FR-16, FR-17, FR-18 | NFR-04, NFR-08 |

## Zasady aktualizacji

- Każda potrzeba powinna mieć źródło w karcie projektu, wywiadzie, dokumencie klienta lub jawnie opisanym założeniu.
- Wymaganie bez potwierdzonego źródła pozostaje hipotezą.
- Zmiana potrzeby powinna powodować przegląd powiązanych FR/NFR oraz otwartych pytań.
- Powiązania z procesami, przypadkami użycia, modelem danych, interfejsem i testami można dodawać wraz z rozwojem dokumentacji.

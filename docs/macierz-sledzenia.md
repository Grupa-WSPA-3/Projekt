# Macierz śledzenia

**Wersja:** 0.1 — robocza

Potrzeby N-xx są na razie hipotezami wyprowadzonymi z karty projektu, ponieważ w przekazanym archiwum nie ma kompletnego protokołu wywiadu. Po rozmowie należy zaktualizować źródła, zachowując nadane identyfikatory.

| Potrzeba | Wymaganie | Historyjka | Priorytet |
|---|---|---|---|
| N-09 | FR-01 Logowanie aktywnego konta | US-01 | Must |
| N-09 | FR-02 Dostęp zgodny z rolą | US-01 | Must |
| N-01, N-04 | FR-03 Lista przyszłych dostępnych terminów | US-02 | Must |
| N-02 | FR-04 Filtrowanie według wykładowcy | — | Should |
| N-02 | FR-05 Filtrowanie według daty | — | Should |
| N-03 | FR-06 Szczegóły terminu | — | Should |
| N-04 | FR-07 Zapis studenta na termin | US-03 | Must |
| N-04 | FR-08 Kontrola limitu przy zapisie | US-03 | Must |
| N-04 | FR-09 Brak duplikatu aktywnego zapisu | US-03 | Must |
| N-05 | FR-10 Anulowanie własnego zapisu | US-04 | Must |
| N-06 | FR-11 Tworzenie terminu | US-05 | Must |
| N-06 | FR-12 Edycja nieobsadzonego terminu | — | Should |
| N-07, N-09 | FR-13 Lista zapisów dla własnego terminu | — | Should |
| N-06 | FR-14 Anulowanie własnej konsultacji | US-06 | Must |
| N-08 | FR-15 Zarządzanie kontami i rolami | — | Should |
| N-10 | FR-16 Wyświetlanie statusu zapisu | — | Should |
| N-10 | FR-17 Komunikat o wyniku operacji | US-03 | Must |
| N-04, N-10 | FR-18 Odrzucenie zapisu na niedostępny termin | — | Should |
| N-01, N-02 | NFR-02 Wydajność wyszukiwania | US-02 (przekrojowo) | Should |
| N-04 | NFR-05 Niezawodność limitu miejsc | US-03 (przekrojowo) | Must |
| N-09 | NFR-06 Bezpieczeństwo i autoryzacja | US-01 (przekrojowo) | Must |
| N-01, N-04 | NFR-08 Widok responsywny | US-02 / US-03 (przekrojowo) | Should |
| N-01, N-04, N-05, N-06, N-09, N-10 | NFR-01 Pokrycie kryteriów Must | US-01…US-06 (przekrojowo) | Must |
| N-01, N-02 | NFR-03 Kompatybilność przeglądarek | US-02 / US-03 (przekrojowo) | Should |
| N-04, N-10 | NFR-04 Użyteczność przepływu zapisu | US-03 | Should |
| N-04, N-05, N-06 | NFR-07 Testowalność reguł biznesowych | US-03 / US-04 / US-05 / US-06 | Should |
| N-06 | BR-01 Poprawny zakres terminu | US-05 | Must / reguła |
| N-04 | BR-02 Limit aktywnych zapisów | US-02 / US-03 | Must / reguła |
| N-04 | BR-03 Brak duplikatu aktywnego zapisu | US-03 | Must / reguła |
| N-05, N-06, N-08, N-09 | BR-04 Właściciel operacji i role | US-01 / US-04 / US-06 | Must / reguła |
| N-06 | BR-05 Edycja tylko nieobsadzonego terminu | — | Should / reguła |
| N-06, N-10 | BR-06 Anulowany termin i powiązane zapisy | US-06 | Must / reguła |
| N-04, N-05 | BR-07 Anulowany zapis zwalnia miejsce | US-03 / US-04 | Must / reguła |
| N-07, N-09 | BR-08 Ograniczenie widoczności listy zapisów | — | Should / reguła |
| N-08, N-09 | BR-09 Jedna podstawowa rola konta | US-01 | Should / reguła |

## Kontrola macierzy

- Każda potrzeba N-01…N-10 ma przypisane co najmniej jedno wymaganie.
- Historyjki Must mają kryteria akceptacji w formacie Given / When / Then w `03-wymagania.md`.
- Puste pole historyjki przy wymaganiu Should oznacza element do dalszego doprecyzowania.
- Kolejne kolumny dotyczące procesów, przypadków użycia, klas, tabel, ekranów, API i testów dodawane są na dalszych etapach przedmiotu.

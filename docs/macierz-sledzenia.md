# Macierz śledzenia

**Wersja:** 0.2 — rozszerzona po walkthrough procesów; robocza

Potrzeby N-xx pozostają hipotezami wyprowadzonymi z karty projektu, ponieważ nie ma kompletnego protokołu rzeczywistego wywiadu. Kolumna „Proces” wskazuje kroki z dokumentacji P-00–P-03. Puste pokrycie procesem oznaczono jako „—” wraz z wyjaśnieniem.

| Potrzeba | Wymaganie | Historyjka | MoSCoW | Proces |
|---|---|---|---|---|
| N-09 | FR-01 Logowanie aktywnego konta | US-01 | Must | P-01.1, P-02.1, P-03.1 |
| N-09 | FR-02 Dostęp zgodny z rolą | US-01 | Must | P-01.1, P-01.6, P-02.1, P-02.4, P-03.1, P-03.4 |
| N-01, N-04 | FR-03 Lista przyszłych dostępnych terminów | US-02 | Must | P-01.2 |
| N-02 | FR-04 Filtrowanie według wykładowcy | — | Should | P-01.3 |
| N-02 | FR-05 Filtrowanie według daty | — | Should | P-01.3 |
| N-03 | FR-06 Szczegóły terminu | — | Should | P-01.4 |
| N-04 | FR-07 Zapis studenta na termin | US-03 | Must | P-01.5, P-01.7 |
| N-04 | FR-08 Kontrola limitu przy zapisie | US-03 | Must | P-01.6–P-01.7 |
| N-04 | FR-09 Brak duplikatu aktywnego zapisu | US-03 | Must | P-01.6–P-01.7 |
| N-05 | FR-10 Anulowanie własnego zapisu | US-04 | Must | P-03.2–P-03.7 |
| N-06 | FR-11 Tworzenie terminu | US-05 | Must | P-02.2–P-02.6 |
| N-06 | FR-12 Edycja nieobsadzonego terminu | — | Should | P-02.3–P-02.6 |
| N-07, N-09 | FR-13 Lista zapisów dla własnego terminu | — | Should | P-02.3, P-02.7 |
| N-06 | FR-14 Anulowanie własnej konsultacji | US-06 | Must | P-02.8–P-02.10 |
| N-08 | FR-15 Zarządzanie kontami i rolami | — | Should | — (zarządzanie kontami jest poza P-00–P-03) |
| N-10 | FR-16 Wyświetlanie statusu zapisu | — | Should | P-02.9–P-02.10, P-03.6–P-03.7 |
| N-10 | FR-17 Komunikat o wyniku operacji zapisu | US-03 | Must | P-01.7–P-01.8 |
| N-04, N-10 | FR-18 Odrzucenie zapisu na niedostępny termin | — | Should | P-01.6–P-01.8 |
| N-01, N-02 | NFR-02 Wydajność wyszukiwania | US-02 (przekrojowo) | Should | P-01.2–P-01.3 |
| N-04 | NFR-05 Niezawodność limitu miejsc | US-03 (przekrojowo) | Must | P-01.6–P-01.7 |
| N-09 | NFR-06 Bezpieczeństwo i autoryzacja | US-01 (przekrojowo) | Must | P-01.1, P-02.1, P-03.1–P-03.4 |
| N-01, N-04 | NFR-08 Widok responsywny | US-02 / US-03 (przekrojowo) | Should | P-01.2–P-01.8 |
| N-01, N-04, N-05, N-06, N-09, N-10 | NFR-01 Pokrycie kryteriów Must | US-01…US-06 (przekrojowo) | Must | P-01–P-03 (kryteria przekrojowe) |
| N-01, N-02 | NFR-03 Kompatybilność przeglądarek | US-02 / US-03 (przekrojowo) | Should | P-01–P-03 (przepływy webowe) |
| N-04, N-10 | NFR-04 Użyteczność przepływu zapisu | US-03 | Should | P-01.2–P-01.8 |
| N-04, N-05, N-06 | NFR-07 Testowalność reguł biznesowych | US-03 / US-04 / US-05 / US-06 | Should | P-01–P-03 (reguły i wyjątki) |
| N-06 | BR-01 Poprawny zakres terminu | US-05 | Must / reguła | P-02.3–P-02.4 |
| N-04 | BR-02 Limit aktywnych zapisów | US-02 / US-03 | Must / reguła | P-01.6–P-01.7 |
| N-04 | BR-03 Brak duplikatu aktywnego zapisu | US-03 | Must / reguła | P-01.6–P-01.7 |
| N-05, N-06, N-08, N-09 | BR-04 Właściciel operacji i role | US-01 / US-04 / US-06 | Must / reguła | P-01.1, P-01.6, P-02.1–P-02.4, P-02.8–P-02.9, P-03.1–P-03.4 |
| N-06 | BR-05 Edycja tylko nieobsadzonego terminu | — | Should / reguła | P-02.3–P-02.6 |
| N-06, N-10 | BR-06 Anulowany termin i powiązane zapisy | US-06 | Must / reguła | P-02.8–P-02.10 |
| N-04, N-05 | BR-07 Anulowany zapis zwalnia miejsce | US-03 / US-04 | Must / reguła | P-03.4–P-03.7 |
| N-07, N-09 | BR-08 Ograniczenie widoczności listy zapisów | — | Should / reguła | P-02.7 |
| N-08, N-09 | BR-09 Jedna podstawowa rola konta | US-01 | Should / reguła | P-01.1, P-02.1, P-03.1 |

## Kontrola macierzy

- Każda potrzeba N-01…N-10 ma przypisane co najmniej jedno wymaganie.
- Każde FR ma wskazany krok procesu albo jawne wyjaśnienie „—”.
- Wymagania NFR są mapowane do procesów przekrojowo, jeżeli nie są pojedynczą czynnością.
- Historyjki Must mają kryteria akceptacji Given / When / Then w pliku 03-wymagania.md.
- FR-15 pozostaje poza P-00–P-03; jest funkcją nadzorczą zarządzania kontami i rolami.
- Pytania bez odpowiedzi pozostają w docs/12-otwarte-kwestie.md i odpowiednich Issues.

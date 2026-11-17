# SKW — System obsługi konsultacji wykładowców

SKW (System obsługi konsultacji wykładowców) to projekt systemu wspierającego organizację konsultacji na uczelni. Student ma przeglądać dostępne terminy i zapisywać się na wybrany termin, a wykładowca — zarządzać własnymi terminami i listami zapisów. Celem jest ograniczenie ręcznej koordynacji oraz ochrona limitów miejsc.

## Zespół

| Osoba | Główna odpowiedzialność | Login |
|---|---|---|
| Maksym Tymoshenko | koordynacja projektu i analiza wymagań | `@mtwspa` |
| Kostiantyn Kyrylenko | model danych i architektura | `@Hryak123` |
| Sofiia Vetvytska | UI/UX i dokumentacja | `@miumeowww` |
| Alina Semeniuk | testowanie i kryteria akceptacji | `@semenukalina89-maker` |

Podział odpowiedzialności ma charakter roboczy i wymaga potwierdzenia przez wszystkich członków zespołu.

## Dokumentacja projektu

| Obszar | Dokument |
|---|---|
| Cel, zakres i interesariusze | [Karta projektu](docs/01-karta-projektu.md) |
| Pojęcia dziedzinowe | [Słownik](docs/02-slownik.md) |
| Wymagania FR, NFR, BR i historyjki | [Specyfikacja wymagań](docs/03-wymagania.md) |
| Procesy AS-IS i TO-BE wraz z diagramami BPMN | [Indeks procesów](docs/04-procesy/README.md) |
| Notatki źródłowe do AS-IS | [Notatki P-00](docs/04-procesy/P-00-as-is-notatki.md) |
| Przypadki użycia | [Dokumentacja przypadków użycia](docs/05-przypadki-uzycia/) |
| Granica i kontekst systemu | [Diagram kontekstu](docs/06-architektura/kontekst.md) |
| Wstępna analiza make-or-buy | [Lista kandydatów](docs/06-architektura/make-or-buy.md) |
| Model dziedzinowy | [Model dziedzinowy](docs/07-model-dziedzinowy/) |
| Baza danych | [Dokumentacja bazy danych](docs/08-baza-danych/) |
| Projekt interfejsu | [Dokumentacja interfejsu](docs/09-interfejs/) |
| Model wdrożenia | [Model wdrożenia](docs/10-model-wdrozenia/) |
| Testowanie | [Plan testów](docs/11-plan-testow/) |
| Pytania wymagające decyzji | [Rejestr otwartych kwestii](docs/12-otwarte-kwestie.md) |
| Ryzyka projektowe | [Rejestr ryzyk](docs/13-ryzyka.md) |
| Powiązania N / FR / NFR / BR / US / procesów | [Macierz śledzenia](docs/macierz-sledzenia.md) |
| Decyzje dotyczące narzędzi | [ADR-001](docs/adr/ADR-001-narzedzia.md) |
| Pytania i zapis rozmowy | [Pytania do klienta](docs/spotkania/pytania-do-klienta.md) · [Protokół wywiadu](docs/spotkania/wywiad-1.md) |

## Stan dokumentacji na koniec zajęć 5

| Element | Wersja / status |
|---|---|
| Specyfikacja wymagań | 0.3 — robocza, po walkthrough procesów |
| Proces P-00 AS-IS | 0.2 — rekonstrukcja robocza; wymaga walidacji |
| Procesy P-01–P-03 TO-BE | 0.1 — opis, źródło BPMN 2.0 i eksport SVG |
| Macierz śledzenia | 0.2 — zawiera kolumnę „Proces” |
| Make-or-buy | 0.1 — wstępna lista kandydatów, materiał przygotowawczy do zajęć 6 |
| Wywiad z klientem | szablon oczekujący na rzeczywiste odpowiedzi; nie wpisano fikcyjnych danych |

**Ważne:** wersje dokumentów są wersjami roboczymi, a nie deklaracją zatwierdzenia przez klienta. Potrzeby, kanały obecnego procesu i reguły oznaczone jako hipotezy wymagają potwierdzenia. Otwarte zmiany są prowadzone w Pull Requests; dokumentacja na `main` staje się kompletna po ich wzajemnym review i scaleniu.

## Zasady pracy

- Zmiany w dokumentacji i diagramach wprowadzamy przez osobne gałęzie i Pull Requests.
- Plik `.bpmn` jest źródłem diagramu; po każdej zmianie trzeba zaktualizować odpowiadający mu eksport `.svg`.
- Identyfikatory FR / NFR / BR / US / P-xx zachowujemy w całej dokumentacji i aktualizujemy macierz śledzenia przy zmianach.
- Nierozstrzygnięte decyzje pozostają w rejestrze otwartych kwestii i w odpowiednich GitHub Issues.

## Narzędzia

Zob. [ADR-001 — Narzędzia pracy projektowej](docs/adr/ADR-001-narzedzia.md).

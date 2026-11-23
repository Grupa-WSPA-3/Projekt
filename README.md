# SKW — System obsługi konsultacji wykładowców

**Przedmiot:** Projekt zespołowy systemu informatycznego cz. 1  
**Stan dokumentacji:** pakiet M1 / 0.5 — przygotowany do wspólnego przeglądu zespołu  
**Wersje szczegółowe artefaktów:** karta 0.3, słownik 0.3, wymagania 0.2; pakiet M1 grupuje je pod wspólną wersją przeglądową 0.5.

## Cel projektu

SKW ma uporządkować zapisy na konsultacje wykładowców w jednym miejscu. Student przegląda dostępne terminy, sprawdza szczegóły i zapisuje się na wybrane miejsce. Wykładowca zarządza własnymi terminami i listą zapisanych osób. System ma ograniczać ręczną wymianę wiadomości i zapobiegać przekroczeniu limitu miejsc.

## Zespół

| Osoba | Główna odpowiedzialność | Login GitHub |
|---|---|---|
| Maksym Tymoshenko | koordynacja, analiza wymagań i spójność dokumentacji | @mtwspa |
| Kostiantyn Kyrylenko | model danych i architektura | @Hryak123 |
| Sofiia Vetvytska | UI/UX, słownik i dokumentacja | @miumeowww |
| Alina Semeniuk | testowanie, kryteria akceptacji i kontrola reguł | @semenukalina89-maker |

## Najważniejsze dokumenty

| Artefakt | Plik |
|---|---|
| Karta projektu | [docs/01-karta-projektu.md](docs/01-karta-projektu.md) |
| Słownik dziedzinowy 0.3 | [docs/02-slownik.md](docs/02-slownik.md) |
| Wymagania 0.2: N, FR, NFR, BR, ograniczenia, historyjki i MoSCoW | [docs/03-wymagania.md](docs/03-wymagania.md) |
| Procesy AS-IS / TO-BE | [docs/04-procesy/README.md](docs/04-procesy/README.md) |
| Macierz śledzenia | [docs/macierz-sledzenia.md](docs/macierz-sledzenia.md) |
| Aktorzy i kandydaci przypadków użycia | [docs/05-przypadki-uzycia/README.md](docs/05-przypadki-uzycia/README.md) |
| C4 L1 — kontekst | [docs/06-architektura/kontekst.md](docs/06-architektura/kontekst.md) |
| C4 L2 — kontenery i wpływ NFR | [docs/06-architektura/kontenery.md](docs/06-architektura/kontenery.md) |
| Make-or-buy | [docs/06-architektura/make-or-buy.md](docs/06-architektura/make-or-buy.md) |
| ADR-001 — narzędzia | [docs/adr/ADR-001-narzedzia.md](docs/adr/ADR-001-narzedzia.md) |
| ADR-002 — modularny monolit | [docs/adr/ADR-002-styl-architektury.md](docs/adr/ADR-002-styl-architektury.md) |
| ADR-003 — rdzeń SKW MAKE | [docs/adr/ADR-003-rdzen-skw-make.md](docs/adr/ADR-003-rdzen-skw-make.md) |
| Backlog M1–M3 | [docs/backlog-m1-m3.md](docs/backlog-m1-m3.md) |
| Checklista M1 / v0.5 | [docs/checklista-m1-v0.5.md](docs/checklista-m1-v0.5.md) |
| Otwarte kwestie Q-01…Q-14 | [docs/12-otwarte-kwestie.md](docs/12-otwarte-kwestie.md) |
| Rejestr ryzyk R-01…R-12 | [docs/13-ryzyka.md](docs/13-ryzyka.md) |

## Stan pakietu M1

- wymagania: 10 potrzeb, 18 FR (10 Must / 8 Should), 8 mierzalnych NFR i 10 BR;
- historyjki: US-01…US-07, wraz z kryteriami GWT dla wymagań Must;
- procesy: P-00 AS-IS oraz P-01, P-02, P-03 TO-BE; każdy ma opis, źródło BPMN i eksport SVG;
- macierz śledzenia: potrzeba → wymaganie → historyjka → priorytet → proces;
- architektura: C4 L1 i L2, wpływ NFR, make-or-buy, ADR-002 i ADR-003;
- ryzyka: 12 pozycji z przyczyną, właścicielem, P×S, reakcją, statusem i powiązanymi Issues;
- przypadki użycia: aktor → US → kandydaci UC;
- szablony Issue i PR znajdują się w .github/.

## Ważne granice v1

W pierwszej wersji nie zakładamy integracji z SSO, serwerem poczty, systemem planu zajęć, wideokonferencjami, płatnościami ani natywną aplikacją mobilną. Dodanie takiej integracji wymaga osobnej decyzji o zakresie, wymaganiach, ryzykach i architekturze.

## Status akceptacji

Pakiet 0.5 jest przygotowany do przeglądu zespołu. Propozycje ADR-002 i ADR-003 wymagają zatwierdzenia zespołu. Konfiguracja faktycznych widoków GitHub Projects, użycie szablonów w nowym PR i utworzenie tagu v0.5 pozostają osobnymi czynnościami do potwierdzenia w GitHub.

## Zasady pracy zespołu

1. Każde zadanie ma GitHub Issue, jednego głównego właściciela i kryteria akceptacji.
2. Powiązane zadania są łączone relacją Parent / Sub-issue lub Blocked by / Blocking, jeżeli istnieje rzeczywista zależność.
3. Zmiany dokumentacji są przeglądane przez co najmniej jedną osobę inną niż autor.
4. W opisie PR używamy Closes #numer wyłącznie wtedy, gdy PR rzeczywiście zamyka dane Issue.
5. Backlog prowadzimy w jednym GitHub Project; widoki M1, M2 i M3 filtrują te same Issues.
6. Statusy Issues, PR, recenzji i commitów muszą odpowiadać rzeczywistym działaniom zespołu.

## Indeks dokumentacji

Pełny indeks: [docs/README.md](docs/README.md)

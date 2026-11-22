# SKW — System obsługi konsultacji wykładowców

**Przedmiot:** Projekt zespołowy systemu informatycznego cz. 1  
**Stan dokumentacji:** komplet roboczy na koniec 5. zajęć (AS-IS / TO-BE)  
**Wersja:** 0.2 wymagań, 0.3 słownika, 0.3 karty projektu

## Cel projektu

SKW ma uporządkować zapisy na konsultacje wykładowców w jednym miejscu. Student przegląda dostępne terminy, sprawdza szczegóły i zapisuje się na wybrane miejsce. Wykładowca zarządza własnymi terminami i listą zapisanych osób. System ma ograniczać ręczną wymianę wiadomości i zapobiegać przekroczeniu limitu miejsc.

## Zespół

| Osoba | Główna odpowiedzialność | Login GitHub |
|---|---|---|
| Maksym Tymoshenko | koordynacja, analiza wymagań i spójność dokumentacji | `@mtwspa` |
| Kostiantyn Kyrylenko | model danych i architektura | `@Hryak123` |
| Sofiia Vetvytska | UI/UX, słownik i dokumentacja | `@miumeowww` |
| Alina Semeniuk | testowanie, kryteria akceptacji i kontrola reguł | `@semenukalina89-maker` |

Podział odpowiedzialności ma charakter roboczy; każdy członek zespołu współpracuje przy przeglądzie dokumentów.

## Najważniejsze dokumenty

| Artefakt | Plik |
|---|---|
| Karta projektu | [docs/01-karta-projektu.md](docs/01-karta-projektu.md) |
| Słownik dziedzinowy 0.3 | [docs/02-slownik.md](docs/02-slownik.md) |
| Wymagania 0.2: N, FR, NFR, BR, ograniczenia, historyjki i MoSCoW | [docs/03-wymagania.md](docs/03-wymagania.md) |
| Procesy AS-IS / TO-BE | [docs/04-procesy/README.md](docs/04-procesy/README.md) |
| Macierz śledzenia z kolumną „Proces” | [docs/macierz-sledzenia.md](docs/macierz-sledzenia.md) |
| Przypadki użycia — zakres wstępny | [docs/05-przypadki-uzycia/README.md](docs/05-przypadki-uzycia/README.md) |
| Diagram kontekstu | [docs/06-architektura/kontekst.md](docs/06-architektura/kontekst.md) |
| Kandydaci make-or-buy | [docs/06-architektura/make-or-buy.md](docs/06-architektura/make-or-buy.md) |
| Otwarte kwestie Q-01…Q-14 | [docs/12-otwarte-kwestie.md](docs/12-otwarte-kwestie.md) |
| Rejestr ryzyk | [docs/13-ryzyka.md](docs/13-ryzyka.md) |
| Checklista kryteriów zajęć 5 | [docs/checklista-zajecia-5.md](docs/checklista-zajecia-5.md) |
| Pytania do klienta | [docs/spotkania/pytania-do-klienta.md](docs/spotkania/pytania-do-klienta.md) |
| Protokół wywiadu | [docs/spotkania/wywiad-1.md](docs/spotkania/wywiad-1.md) |
| Decyzja o narzędziach | [docs/adr/ADR-001-narzedzia.md](docs/adr/ADR-001-narzedzia.md) |

## Zakres opracowany do etapu 5

- karta projektu, interesariusze, role oraz zakres IN/OUT;
- słownik dziedzinowy z definicjami, synonimami, homonimami i źródłami;
- lista potrzeb N-01…N-10 i specyfikacja 18 FR (10 Must / 8 Should), 8 mierzalnych NFR według kategorii ISO/IEC 25010:2023 oraz 10 reguł BR;
- siedem historyjek użytkownika (US-01…US-07), w tym scenariusze Given/When/Then dla wszystkich wymagań Must; 
- proces AS-IS w BPMN (źródło + SVG) oraz trzy procesy TO-BE;
- proces P-00 AS-IS i główny proces P-01 TO-BE w BPMN 2.0: źródła `.bpmn` i eksporty `.svg`;
- macierz śledzenia: potrzeba → wymaganie → historyjka → priorytet → krok procesu;
- otwarte pytania, rejestr ryzyk, Issues i zasady pracy z PR.

## Status wiarygodności

**Dokumentacja jest spójna roboczo, ale nie wszystkie założenia są potwierdzone przez klienta.** W udostępnionych materiałach nie znaleziono rzeczywistego protokołu wywiadu z odpowiedziami i dosłownymi cytatami. Dlatego proces AS-IS, potrzeby i część reguł zostały oznaczone jako hipotezy zespołu. Nie dopisano fikcyjnych wypowiedzi klienta. Przed uznaniem specyfikacji za ostateczną należy uzupełnić `docs/spotkania/wywiad-1.md` na podstawie faktycznych notatek z zajęć.

## Zasady pracy zespołu

1. Każde zadanie ma GitHub Issue, jednego właściciela i kryterium akceptacji.
2. Zmiany dokumentacji są wprowadzane przez osobną gałąź i Pull Request.
3. Każdy PR powinien być sprawdzony przez co najmniej jedną inną osobę; autor nie zatwierdza własnych zmian.
4. W opisie PR używamy `Closes #numer` wyłącznie wtedy, gdy praca rzeczywiście zamyka dane Issue.
5. Backlog prowadzimy w GitHub Projects, a zadania źródłowe w Issues.
6. Statusy Issues, PR, recenzji i commitów muszą odpowiadać rzeczywistym działaniom zespołu.

## Struktura repozytorium

- `docs/01–03` — karta, słownik i wymagania;
- `docs/04` — procesy biznesowe AS-IS / TO-BE;
- `docs/05` — wstępne przypadki użycia;
- `docs/06` — kontekst i analiza make-or-buy;
- `docs/07–11` — artefakty kolejnych etapów modelowania, implementacji i testowania;
- `docs/12–13` — otwarte kwestie i ryzyka;
- `docs/adr` — decyzje architektoniczne i organizacyjne;
- `docs/spotkania` — pytania, notatki i protokoły.


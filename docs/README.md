# SKW — System obsługi konsultacji wykładowców

**Przedmiot:** Projekt zespołowy systemu informatycznego cz. 1  
**Wersja dokumentacji:** 0.4 (robocza)

## O projekcie

SKW ma uporządkować zapisy na konsultacje wykładowców w jednym miejscu. Student sprawdza dostępne terminy i zapisuje się na wybrany termin, a wykładowca zarządza własnymi konsultacjami oraz listą zapisanych osób. System powinien zapobiegać przekroczeniu limitu miejsc i ograniczać ręczną wymianę wiadomości.

Repozytorium zawiera dokumentację analityczną i projektową oraz docelową strukturę katalogów wskazaną w materiałach przedmiotu. Katalogi dotyczące dalszych etapów pozostają celowo puste — będą uzupełniane po omówieniu odpowiednich zagadnień. `src/` i `tests/` również pozostają puste zgodnie z instrukcją przedmiotu.

**Uwaga dotycząca źródeł:** w przekazanym archiwum zespołu nie było kompletnego, rzeczywistego protokołu wywiadu. Dlatego `wywiad-1.md` zawiera szablon do uzupełnienia, a potrzeby w wymaganiach są oznaczone jako hipotezy do potwierdzenia. Nie wpisano fikcyjnych cytatów ani odpowiedzi klienta.

## Zespół

| Osoba | Główna odpowiedzialność | Login GitHub |
|---|---|---|
| Maksym Tymoshenko | koordynacja, analiza wymagań, spójność dokumentacji | `user123876t14987` |
| Kostiantyn Kyrylenko | model danych, architektura, wsparcie implementacji | `Hryak123` |
| Sofiia Vetvytska | UI/UX, słownik, dokumentacja | `miumeowww` |
| Alina Semeniuk | testowanie, kryteria akceptacji, kontrola reguł | `semenukalina89-maker` |

Podział odpowiedzialności jest propozycją zespołu i powinien być potwierdzony przez wszystkich członków.

## Dokumentacja przygotowana na obecnym etapie

- [Karta projektu](docs/01-karta-projektu.md)
- [Słownik dziedzinowy](docs/02-slownik.md)
- [Specyfikacja wymagań: potrzeby, FR, NFR, BR, historyjki i MoSCoW](docs/03-wymagania.md)
- [Notatki do procesu AS-IS](docs/04-procesy/P-00-as-is-notatki.md)
- [Diagram kontekstu](docs/06-architektura/kontekst.md)
- [Otwarte kwestie](docs/12-otwarte-kwestie.md)
- [Rejestr ryzyk](docs/13-ryzyka.md)
- [Macierz śledzenia](docs/macierz-sledzenia.md)
- [ADR-001 — narzędzia pracy projektowej](docs/adr/ADR-001-narzedzia.md)
- [Pytania do klienta](docs/spotkania/pytania-do-klienta.md)
- [Protokół wywiadu](docs/spotkania/wywiad-1.md)

## Struktura repozytorium

- `docs/01–03` — karta projektu, słownik i wymagania.
- `docs/04–06` — procesy, przypadki użycia i architektura; na tym etapie przygotowane są notatki AS-IS oraz diagram kontekstu, a katalog przypadków użycia pozostaje pusty.
- `docs/07–11` — przyszłe artefakty: model dziedzinowy, baza danych, interfejs, model wdrożenia i plan testów. Katalogi pozostają puste do odpowiednich etapów.
- `docs/12–13` — otwarte kwestie i ryzyka.
- `docs/adr/` — decyzje projektowe.
- `docs/spotkania/` — pytania i protokoły spotkań.
- `src/` i `tests/` — przygotowane katalogi na późniejszą pracę implementacyjną.

## Zasady pracy zespołu

1. Repozytorium jest wspólnym źródłem aktualnej dokumentacji.
2. Każde zadanie powinno mieć osobne GitHub Issue, jednego właściciela i sprawdzalny rezultat.
3. Zmiany w dokumentacji wprowadzamy przez gałąź i Pull Request.
4. Każdy PR powinien zostać zrecenzowany przez co najmniej jedną inną osobę; autor nie zatwierdza własnej zmiany.
5. W opisie PR stosujemy `Closes #numer`, gdy praca rzeczywiście zamyka wskazane Issue.
6. Backlog produktu prowadzimy w GitHub Projects, a nie jako osobną listę zastępującą Issues.
7. Statusy Issues, PR, recenzji i commitów muszą odpowiadać rzeczywistym działaniom zespołu.

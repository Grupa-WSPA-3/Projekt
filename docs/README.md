# Indeks dokumentacji SKW

Dokumentacja opisuje zakres, wymagania, procesy biznesowe, model architektury ogólnej, decyzje i backlog M1–M3. Pakiet M1 ma wersję przeglądową 0.5; wersje szczegółowe artefaktów pozostają widoczne w ich nagłówkach.

## Dokumenty główne

| Dokument | Zawartość |
|---|---|
| [01-karta-projektu.md](01-karta-projektu.md) | problem, cel, role, interesariusze, IN/OUT, założenia |
| [02-slownik.md](02-slownik.md) | słownik dziedzinowy, definicje, synonimy, homonimy |
| [03-wymagania.md](03-wymagania.md) | N-xx, FR, NFR, BR, ograniczenia, historyjki GWT, MoSCoW |
| [macierz-sledzenia.md](macierz-sledzenia.md) | powiązania N → FR → US → priorytet → proces |
| [backlog-m1-m3.md](backlog-m1-m3.md) | widoki tabelaryczne M1–M3, Issues i zależności |
| [checklista-m1-v0.5.md](checklista-m1-v0.5.md) | kontrola pakietu M1 i czynności wymagające potwierdzenia |
| [12-otwarte-kwestie.md](12-otwarte-kwestie.md) | pytania Q-01…Q-14, właściciele, status i Issues |
| [13-ryzyka.md](13-ryzyka.md) | rejestr ryzyk z P×S, przyczyną, właścicielem i reakcją |

## Procesy — 04-procesy/

- [README.md](04-procesy/README.md) — indeks procesów;
- [P-00-as-is-notatki.md](04-procesy/P-00-as-is-notatki.md) — AS-IS, punkty bólu i kwestie do walidacji;
- P-00: [BPMN](04-procesy/P-00-rezerwacja-as-is.bpmn) i [SVG](04-procesy/P-00-rezerwacja-as-is.svg);
- P-01: [opis](04-procesy/P-01-rezerwacja-konsultacji.md), [BPMN](04-procesy/P-01-rezerwacja-konsultacji.bpmn), [SVG](04-procesy/P-01-rezerwacja-konsultacji.svg);
- P-02: [opis](04-procesy/P-02-zarzadzanie-terminami.md), [BPMN](04-procesy/P-02-zarzadzanie-terminami.bpmn), [SVG](04-procesy/P-02-zarzadzanie-terminami.svg);
- P-03: [opis](04-procesy/P-03-anulowanie-zapisu.md), [BPMN](04-procesy/P-03-anulowanie-zapisu.bpmn), [SVG](04-procesy/P-03-anulowanie-zapisu.svg).

## Przypadki użycia

- [05-przypadki-uzycia/README.md](05-przypadki-uzycia/README.md) — aktorzy, mapowanie US → UC, katalog przypadków użycia i scenariusz UC-05.

## Architektura — 06-architektura/

- [kontekst.md](06-architektura/kontekst.md) — C4 poziom 1: kontekst i tabela elementów;
- [kontenery.md](06-architektura/kontenery.md) — C4 poziom 2, kontenery, protokoły i wpływ NFR;
- [make-or-buy.md](06-architektura/make-or-buy.md) — porównanie obszarów z kryteriami dopasowania, kosztu, ryzyka, zależności, RODO i czasu.

## Decyzje architektoniczne — adr/

- [ADR-001-narzedzia.md](adr/ADR-001-narzedzia.md) — narzędzia pracy projektowej;
- [ADR-002-styl-architektury.md](adr/ADR-002-styl-architektury.md) — modularny monolit;
- [ADR-003-rdzen-skw-make.md](adr/ADR-003-rdzen-skw-make.md) — własny rdzeń domenowy SKW.

## Pozostałe obszary

- [07-model-dziedzinowy/README.md](07-model-dziedzinowy/README.md) — szkic pojęć i relacji dziedzinowych;
- [08-baza-danych/README.md](08-baza-danych/README.md) — wstępny model logiczny danych;
- [09-interfejs/README.md](09-interfejs/README.md) — role, widoki i zasady UI;
- [10-model-wdrozenia/README.md](10-model-wdrozenia/README.md) — logiczny model wdrożenia;
- [11-plan-testow/README.md](11-plan-testow/README.md) — katalog scenariuszy testowych;
- [spotkania/pytania-do-klienta.md](spotkania/pytania-do-klienta.md) — pytania do wywiadu;
- [spotkania/wywiad-1.md](spotkania/wywiad-1.md) — protokół do uzupełnienia rzeczywistymi danymi.

## Szablony pracy

- [Szablon zadania](../.github/ISSUE_TEMPLATE/zadanie.md)
- [Szablon pytania do klienta](../.github/ISSUE_TEMPLATE/pytanie-do-klienta.md)
- [Szablon Pull Request](../.github/pull_request_template.md)

## Konwencje

1. Potrzeby mają identyfikatory N-xx, wymagania FR-xx, NFR-xx, reguły BR-xx, historyjki US-xx, procesy P-xx, kroki P-xx.n, ryzyka R-xx, decyzje ADR-xxx.
2. Każde FR ma źródło potrzeby oraz powiązanie z historyjką i krokiem procesu albo jawne uzasadnienie braku mapowania.
3. Hipotezy zespołu są odróżniane od ustaleń potwierdzonych.
4. Diagram BPMN i eksport SVG muszą przedstawiać tę samą wersję procesu.
5. Zmiana wymagania lub procesu wymaga aktualizacji macierzy śledzenia.

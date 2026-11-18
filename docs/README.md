# Indeks dokumentacji SKW

Dokumentacja przedstawia zakres i model rozwiązania na poziomie roboczym po opracowaniu wymagań oraz procesów AS-IS / TO-BE. Wymagania i procesy mają identyfikatory, źródła oraz powiązania w macierzy śledzenia.

## Dokumenty główne

| Dokument | Zawartość |
|---|---|
| [01-karta-projektu.md](01-karta-projektu.md) | problem, cel, role, interesariusze, IN/OUT, założenia |
| [02-slownik.md](02-slownik.md) | słownik 0.3: definicje, synonimy, homonimy, przykłady i źródła |
| [03-wymagania.md](03-wymagania.md) | N-xx, FR, NFR, BR, ograniczenia, historyjki GWT, MoSCoW |
| [macierz-sledzenia.md](macierz-sledzenia.md) | powiązania N → FR → US → priorytet → proces |
| [12-otwarte-kwestie.md](12-otwarte-kwestie.md) | pytania Q-01…Q-14, właściciele, status i linki do Issues |
| [13-ryzyka.md](13-ryzyka.md) | rejestr ryzyk z prawdopodobieństwem, wpływem, właścicielem i reakcją |

## Procesy — `04-procesy/`

- [README.md](04-procesy/README.md) — indeks i konwencja numerowania;
- [P-00-as-is-notatki.md](04-procesy/P-00-as-is-notatki.md) — hipotetyczny AS-IS, punkty bólu i kwestie do walidacji;
- [P-01-rezerwacja-konsultacji.md](04-procesy/P-01-rezerwacja-konsultacji.md) — główny TO-BE: przeglądanie i zapis;
- [P-01-rezerwacja-konsultacji.bpmn](04-procesy/P-01-rezerwacja-konsultacji.bpmn) — źródło BPMN 2.0;
- [P-01-rezerwacja-konsultacji.svg](04-procesy/P-01-rezerwacja-konsultacji.svg) — eksport diagramu BPMN;
- [P-02-zarzadzanie-terminami.md](04-procesy/P-02-zarzadzanie-terminami.md) — TO-BE: zarządzanie terminami przez wykładowcę;
- [P-03-anulowanie-zapisu.md](04-procesy/P-03-anulowanie-zapisu.md) — TO-BE: anulowanie własnego zapisu przez studenta.

## Pozostałe obszary

- [05-przypadki-uzycia/README.md](05-przypadki-uzycia/README.md) — wstępne scenariusze UC wynikające z FR;
- [06-architektura/kontekst.md](06-architektura/kontekst.md) — diagram kontekstu i granica systemu;
- [06-architektura/make-or-buy.md](06-architektura/make-or-buy.md) — lista kandydatów do dalszej analizy;
- [07-model-dziedzinowy/README.md](07-model-dziedzinowy/README.md) — szkic pojęć i relacji dziedzinowych;
- [08-baza-danych/README.md](08-baza-danych/README.md) — wstępny model logiczny danych i ograniczenia integralności;
- [09-interfejs/README.md](09-interfejs/README.md) — role, widoki i zasady UI;
- [10-model-wdrozenia/README.md](10-model-wdrozenia/README.md) — wariant logiczny wdrożenia bez przesądzania technologii;
- [11-plan-testow/README.md](11-plan-testow/README.md) — katalog scenariuszy wynikających z FR / BR / NFR;
- [adr/ADR-001-narzedzia.md](adr/ADR-001-narzedzia.md) — narzędzia i sposób pracy.

## Spotkania i pytania

- [spotkania/pytania-do-klienta.md](spotkania/pytania-do-klienta.md) — 25 pytań do wywiadu;
- [spotkania/wywiad-1.md](spotkania/wywiad-1.md) — protokół do uzupełnienia rzeczywistymi danymi.

## Konwencje

1. Potrzeby mają identyfikatory `N-xx`, wymagania `FR-xx`, `NFR-xx`, reguły `BR-xx`, historyjki `US-xx`, procesy `P-xx`, kroki `P-xx.n`.
2. Każde FR ma źródło potrzeby oraz powiązanie z historyjką i krokiem procesu albo jawne uzasadnienie braku mapowania.
3. Hipotezy zespołu są odróżniane od ustaleń potwierdzonych przez klienta.
4. Diagram BPMN i jego eksport SVG muszą przedstawiać tę samą wersję procesu.
5. Zmiana wymagania lub procesu wymaga aktualizacji macierzy śledzenia.


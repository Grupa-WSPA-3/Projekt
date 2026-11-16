# Procesy biznesowe SKW

Dokumentacja obejmuje obecną organizację konsultacji (AS-IS) oraz procesy docelowe po wprowadzeniu SKW (TO-BE). Każdy proces ma opis kroków, wyjątki i identyfikatory P-xx.n. W procesach TO-BE kroki są powiązane z FR/BR; w AS-IS kroki wskazują potrzeby i punkty bólu, które są następnie mapowane na rozwiązania TO-BE.

## Katalog procesów

| ID | Proces | Typ | Opis kroków | Źródło BPMN 2.0 | Eksport SVG | Właściciel / Issue |
|---|---|---|---|---|---|---|
| P-00 | Obecna organizacja konsultacji | AS-IS | [P-00](P-00-rezerwacja-as-is.md) | [BPMN](P-00-rezerwacja-as-is.bpmn) | [SVG](P-00-rezerwacja-as-is.svg) | @mtwspa · [#4](https://github.com/Grupa-WSPA-3/Projekt/issues/4) |
| P-01 | Przeglądanie i zapis na konsultację | TO-BE | [P-01](P-01-rezerwacja-konsultacji.md) | [BPMN](P-01-rezerwacja-konsultacji.bpmn) | [SVG](P-01-rezerwacja-konsultacji.svg) | @Hryak123 · [#5](https://github.com/Grupa-WSPA-3/Projekt/issues/5) |
| P-02 | Zarządzanie terminami przez wykładowcę | TO-BE | [P-02](P-02-zarzadzanie-terminami.md) | [BPMN](P-02-zarzadzanie-terminami.bpmn) | [SVG](P-02-zarzadzanie-terminami.svg) | @miumeowww · [#6](https://github.com/Grupa-WSPA-3/Projekt/issues/6) |
| P-03 | Anulowanie własnego zapisu przez studenta | TO-BE | [P-03](P-03-anulowanie-zapisu.md) | [BPMN](P-03-anulowanie-zapisu.bpmn) | [SVG](P-03-anulowanie-zapisu.svg) | @semenukalina89-maker · [#7](https://github.com/Grupa-WSPA-3/Projekt/issues/7) |

## Standard dokumentacji procesu

Każdy opis procesu powinien zawierać: cel, wyzwalacz, uczestników, wyniki, diagram BPMN 2.0, tabelę ponumerowanych kroków, wyjątki i ścieżki alternatywne, powiązania z AS-IS / TO-BE oraz otwarte pytania. Numer kroku ma postać `P-xx.n` i jest używany w macierzy śledzenia.

## Kontrola diagramów BPMN

- Diagram rozpoczyna się zdarzeniem startowym i ma odrębne zdarzenia końcowe dla różnych wyników.
- Wyjścia z bramek decyzyjnych mają opisane warunki (np. „tak” / „nie” albo konkretną przyczynę).
- Tory przedstawiają role uczestników procesu; działania wykonywane automatycznie przypisano do toru „System SKW”.
- Główne procesy TO-BE pokazują wyjątki, a nie tylko idealną ścieżkę.
- Źródło `.bpmn` i eksport `.svg` przedstawiają tę samą wersję diagramu. Po zmianie źródła należy wygenerować nowy eksport.

## Zasady interpretacji

- **AS-IS** opisuje sposób obecny, a **TO-BE** — sposób docelowy po wdrożeniu SKW.
- Nie przenosimy identyfikatorów i wymagań z obcych przykładów; używamy wyłącznie identyfikatorów SKW.
- Punkty bólu AS-IS powinny mieć odpowiedź w procesie TO-BE albo jawną decyzję o pozostawieniu poza zakresem.
- Hipotezy zespołu są wyraźnie odróżnione od informacji potwierdzonych przez klienta.
- Wszystkie zmiany procesu wymagające zmiany FR / BR muszą być odzwierciedlone w `docs/03-wymagania.md` i `docs/macierz-sledzenia.md`.

## Status źródłowy

W przekazanych materiałach nie ma wypełnionego protokołu rzeczywistego wywiadu. P-00 oraz niepotwierdzone założenia wymagają walidacji; nie są przedstawiane jako fakty potwierdzone przez klienta.

# Procesy biznesowe SKW — indeks

**Wersja:** 0.2 — model roboczy po analizie na etapie 5  
**Legenda źródeł:** „hipoteza zespołu” oznacza rekonstrukcję do walidacji, nie potwierdzony fakt z wywiadu.

## Zestaw procesów

| ID | Proces | Typ | Główna rola | Pliki |
|---|---|---|---|---|
| P-00 | Obecny sposób uzgadniania konsultacji | AS-IS — hipoteza do walidacji | Student, Wykładowca | [notatki](P-00-as-is-notatki.md), [BPMN 2.0](P-00-rezerwacja-as-is.bpmn), [SVG](P-00-rezerwacja-as-is.svg) |
| P-01 | Przeglądanie i zapis na konsultację | TO-BE — proces główny | Student, System SKW | [opis i kroki](P-01-rezerwacja-konsultacji.md), [BPMN 2.0](P-01-rezerwacja-konsultacji.bpmn), [SVG](P-01-rezerwacja-konsultacji.svg) |
| P-02 | Zarządzanie terminami przez wykładowcę | TO-BE — proces pomocniczy | Wykładowca, System SKW | [opis i kroki](P-02-zarzadzanie-terminami.md), [BPMN 2.0](P-02-zarzadzanie-terminami.bpmn), [SVG](P-02-zarzadzanie-terminami.svg) |
| P-03 | Anulowanie własnego zapisu | TO-BE — proces pomocniczy | Student, System SKW | [opis i kroki](P-03-anulowanie-zapisu.md), [BPMN 2.0](P-03-anulowanie-zapisu.bpmn), [SVG](P-03-anulowanie-zapisu.svg) |

## Konwencje modelowania

1. Numer procesu ma format `P-xx`, a krok — `P-xx.n`.
2. Nazwy kroków opisują czynność biznesową lub reakcję systemu; nie opisują kliknięć w interfejsie.
3. Tory oznaczają role lub system SKW, a nie działy organizacji.
4. Bramki mają jawne pytania, a ich wyjścia są podpisane.
5. Różne wyniki procesu kończą się odrębnymi zdarzeniami końcowymi.
6. Każdy krok systemowy jest powiązany z FR lub ma jawne uzasadnienie braku mapowania.
7. Pliki BPMN i eksport SVG dotyczą tej samej wersji odpowiedniego procesu P-00 / P-01.

## Założenia i zakres walidacji

- P-00 jest hipotetyczną rekonstrukcją wynikającą z karty projektu. Rzeczywisty sposób pracy trzeba potwierdzić z osobą znającą organizację konsultacji.
- P-01 zakłada, że limit miejsc jest przechowywany przy terminie i sprawdzany ponownie w momencie zatwierdzenia zapisu.
- P-02 zakłada, że wykładowca nie może zmienić daty/godziny terminu z aktywnymi zapisami w pierwszej wersji.
- P-03 zakłada, że student może anulować własny aktywny zapis; termin graniczny anulowania pozostaje pytaniem Q-03.
- Nie modelowano zewnętrznej poczty, SSO ani planu zajęć, ponieważ są poza zakresem v1.


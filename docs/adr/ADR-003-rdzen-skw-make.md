# ADR-003: Rdzeń domenowy SKW realizujemy samodzielnie (MAKE)

**Status:** propozycja do zatwierdzenia przez zespół  
**Data:** 2026-11-23  
**Autorzy:** zespół SKW  
**Typ decyzji:** make-or-buy

## Kontekst

Główną wartością SKW jest nie samo wyświetlanie kalendarza, lecz zestaw reguł specyficznych dla konsultacji wykładowców:
- Student może zapisać się wyłącznie na dostępny termin;
- liczba aktywnych zapisów nie może przekroczyć limitu;
- limit jest sprawdzany ponownie w chwili zatwierdzania zapisu;
- nie można utworzyć duplikatu aktywnego zapisu tego samego studenta na ten sam termin;
- student anuluje wyłącznie własny zapis;
- wykładowca zarządza wyłącznie własnymi terminami;
- anulowanie terminu musi być widoczne w statusach powiązanych zapisów.

Są to reguły opisane w FR-02…FR-18 i BR-01…BR-10. Gotowa usługa rezerwacyjna mogłaby zapewniać ogólny kalendarz, lecz jej dopasowanie do reguł, modelu ról i statusów nie zostało potwierdzone.

## Rozważane opcje

1. **BUY — gotowy SaaS do rezerwacji:** szybki start, ale trzeba sprawdzić, czy produkt obsługuje ograniczenia, role, statusy, eksport danych i zasady przetwarzania.
2. **MAKE — własny rdzeń domenowy:** zespół projektuje procesy, API i model danych SKW, korzystając z gotowej relacyjnej bazy i bibliotek wspierających.
3. **USE — ogólne biblioteki UI / infrastruktury:** wykorzystanie gotowych komponentów dla elementów niedomenowych po weryfikacji licencji i dostępności.

## Decyzja

**Proponowany wybór: MAKE dla logiki terminów, dostępności, zapisów, anulowania i kontroli uprawnień.**

Nie kupujemy gotowego SaaS jako rdzenia SKW na tym etapie. Wykorzystujemy gotowy silnik relacyjnej bazy danych i — po przeglądzie — standardowe biblioteki pomocnicze. Nie oznacza to budowania własnego silnika bazy danych, protokołów sieciowych ani kryptografii.

## Ocena według kryteriów

| Kryterium | Ocena decyzji MAKE |
|---|---|
| Dopasowanie | własne FR/BR można realizować bez ograniczeń niezweryfikowanego produktu; SaaS wymagałby weryfikacji i ewentualnego dostosowania |
| Koszt | brak potwierdzonych ofert SaaS; nie można rzetelnie podać kwoty; własna realizacja wymaga pracy i utrzymania |
| Ryzyko | odpowiedzialność za reguły i testy spoczywa na zespole; unika się uzależnienia krytycznego procesu od niezweryfikowanego dostawcy |
| Zależność od dostawcy | reguły i dane pozostają w modelu SKW; wymiana silnika bazy wymaga uwzględnienia dialektu SQL i testów |
| RODO | dane studentów nie trafiają do zewnętrznego SaaS bez odrębnej oceny; dostęp i zakres danych kontroluje SKW |
| Czas | budowa jest dłuższa niż uruchomienie gotowego kalendarza, ale ogranicza czas dopasowania i ryzyko obchodzenia reguł |

## Konsekwencje

### Korzyści
- reguły BR-02, BR-03, BR-04, BR-07 i BR-10 są realizowane w jednym miejscu;
- kontrolę współbieżności i dostępów można dopasować do SKW;
- model danych i statusy nie zależą od nieznanego API dostawcy.

### Koszty i ryzyka
- zespół odpowiada za projekt, testy, bezpieczeństwo i utrzymanie rdzenia;
- kontrola limitu nie może ograniczać się do UI;
- konieczne są testy współbieżności, uprawnień i scenariuszy negatywnych;
- hosting, retencja i mechanizm kont wymagają dalszych decyzji.

## Co pozostaje otwarte

- sposób tworzenia kont i odzyskiwania dostępu — Q-05;
- ewentualna integracja z SSO lub planem zajęć — Q-12; poza v1;
- dostępność środowiska wdrożeniowego i warunki hostingu;
- wybór konkretnego silnika i bibliotek po sprawdzeniu środowiska i licencji.

## Powiązania

- [Wymagania](../03-wymagania.md)
- [Proces P-01](../04-procesy/P-01-rezerwacja-konsultacji.md)
- [Proces P-02](../04-procesy/P-02-zarzadzanie-terminami.md)
- [Proces P-03](../04-procesy/P-03-anulowanie-zapisu.md)
- [Make-or-buy](../06-architektura/make-or-buy.md)
- [Rejestr ryzyk](../13-ryzyka.md)

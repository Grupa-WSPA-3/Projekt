# Checklista M1 — pakiet dokumentacji v0.5

**Wersja pakietu:** 0.5  
**Stan:** przygotowany do wspólnego przeglądu zespołu.

| # | Kryterium | Lokalizacja | Stan |
|---:|---|---|---|
| 1 | karta projektu i zakres IN/OUT | [01-karta-projektu.md](01-karta-projektu.md) | [x] karta 0.3 |
| 2 | słownik z terminami, synonimami i homonimami | [02-slownik.md](02-slownik.md) | [x] słownik 0.3 |
| 3 | lista potrzeb N-01… | [03-wymagania.md](03-wymagania.md) | [x] N-01…N-10 |
| 4 | FR z MoSCoW, mierzalne NFR i reguły BR | [03-wymagania.md](03-wymagania.md) | [x] 18 FR, 8 NFR, 10 BR |
| 5 | historyjki GWT dla wszystkich Must | [03-wymagania.md](03-wymagania.md) | [x] US-01…US-07 |
| 6 | procesy: AS-IS i 2–3 TO-BE | [04-procesy/](04-procesy/README.md) | [x] P-00 + P-01, P-02, P-03 |
| 7 | macierz potrzeba → wymaganie → historyjka → proces | [macierz-sledzenia.md](macierz-sledzenia.md) | [x] istnieje; aktualizować po zmianach FR/BR |
| 8 | C4 L1 z tabelą elementów i relacji | [kontekst.md](06-architektura/kontekst.md) | [x] przygotowano; właściciel biznesowy wymaga potwierdzenia |
| 9 | C4 L2 z technologią kontenerów i protokołami | [kontenery.md](06-architektura/kontenery.md) | [x] przygotowano; frameworki i środowisko do decyzji |
| 10 | wpływ co najmniej 4 NFR na architekturę | [kontenery.md](06-architektura/kontenery.md) | [x] opisano NFR-01…NFR-08 |
| 11 | make-or-buy co najmniej 4 obszarów | [make-or-buy.md](06-architektura/make-or-buy.md) | [x] oceniono 6 obszarów |
| 12 | ADR stylu architektury i ADR make-or-buy | [adr/](adr/) | [x] dodano ADR-002 i ADR-003 jako propozycje do zatwierdzenia |
| 13 | rejestr co najmniej 6 ryzyk: projektowe i produktowe | [13-ryzyka.md](13-ryzyka.md) | [x] 12 ryzyk z P, S, P×S, przyczyną, reakcją, właścicielem i statusem |
| 14 | aktor → US → kandydaci UC | [05-przypadki-uzycia/README.md](05-przypadki-uzycia/README.md) | [x] Student, Wykładowca, Administrator; US-01…US-07; UC-01…UC-11 |
| 15 | szablony Issue i PR zapisane w repozytorium | [.github/](../.github/) | [x] szablony dodane |
| 16 | szablony użyte w co najmniej jednym nowym Issue i PR | [Issue #34](https://github.com/Grupa-WSPA-3/Projekt/issues/34) | [ ] wymaga rzeczywistego PR utworzonego z szablonu i recenzji |
| 17 | GitHub Projects z widokami M1–M3 i zależnościami | [backlog-m1-m3.md](backlog-m1-m3.md), [Issue #32](https://github.com/Grupa-WSPA-3/Projekt/issues/32) | [ ] wymaga konfiguracji w interfejsie GitHub Projects |
| 18 | tag v0.5 na zatwierdzonym commicie M1 | Tags / Releases | [ ] tworzyć po przeglądzie, nie przed nim |

## Warunki publikacji v0.5

1. Zespół sprawdza dokumenty, identyfikatory FR/NFR/BR/US/P/ADR i linki.
2. Co najmniej jedna osoba inna niż autor przeprowadza recenzję.
3. GitHub Projects zawiera otwarte Issues z właścicielami, statusami i etapami M1–M3.
4. Tag v0.5 wskazuje zatwierdzony commit M1 na main. Po utworzeniu tagu nie przesuwa się go; poprawki trafiają do kolejnej wersji.

## Ważne ograniczenia

- [x] oznacza przygotowanie artefaktu w repozytorium, a nie akceptację przez prowadzącego.
- ADR-002 i ADR-003 są propozycjami do zatwierdzenia przez zespół.
- Integracje SSO, poczty i planu zajęć nie są dopisywane do v1 bez decyzji i zmiany zakresu.
- P-00 i potrzeby nie mogą być przedstawiane jako potwierdzone ustalenia bez odpowiedniego potwierdzenia.

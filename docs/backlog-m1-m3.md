# Backlog projektu SKW — M1 / M2 / M3

**Wersja pakietu:** M1 / 0.5  
**Zasada:** jedno Issue jest jednym zadaniem źródłowym. Widoki M1, M2 i M3 filtrują ten sam zestaw elementów — nie tworzą kopii Issues.

## Widoki tabelaryczne GitHub Projects

Utworzyć jeden GitHub Project dla repozytorium SKW i dodać widoki typu **Table**:

| Widok | Filtr | Co pokazuje |
|---|---|---|
| 00 — Wszystkie Issues | bez filtra etapu | cały backlog zespołu |
| 01 — M1: Specyfikacja wymagań | Milestone = M1 | wymagania, procesy, C4, ADR, ryzyka, UC i organizacja pracy |
| 02 — M2: Projekt techniczny | Milestone = M2 | doprecyzowanie modelu technicznego i otwartych decyzji |
| 03 — M3: Projekt kompletny | Milestone = M3 | implementacja, testy i kompletacja projektu |

Widoki korzystają z tej samej kolekcji Issues. Gdy zmienisz pole Milestone z M1 na M2, zadanie znika z widoku M1 i pojawia się w M2. Gdy zmienisz Status z Todo na In progress, zmienia się jego pozycja / grupa statusu we wszystkich widokach. Nie kopiujemy Issue do drugiej tabeli.

## Zalecane pola Project

| Pole | Typ / wartości | Zastosowanie |
|---|---|---|
| Status | Todo / In progress / Review / Done | rzeczywisty etap wykonania |
| Assignees | użytkownicy GitHub | jeden główny właściciel |
| Priority | P0 / P1 / P2 | kolejność realizacji |
| Milestone | M1 / M2 / M3 | etap / widok projektu |
| Type | Epic / Task / Question / Risk | rodzaj elementu |
| Parent / Sub-issue | relacja Issue | podział większej pracy na mniejsze zadania |
| Blocked by / Blocking | relacja zależności | wskazuje, co musi zostać zakończone wcześniej |

Status „Done” stosować dopiero po spełnieniu kryteriów akceptacji i przeglądzie. Samo powiązanie tematyczne nie oznacza blokady.

## M1 — Specyfikacja wymagań

**Cel:** gotowa do przeglądu specyfikacja, procesy, architektura ogólna, decyzje, ryzyka i backlog.

| Issue | Zadanie | Powiązanie / zależność |
|---|---|---|
| [#3](https://github.com/Grupa-WSPA-3/Projekt/issues/3) | uporządkowanie Issues i organizacji pracy | cała tablica M1–M3 |
| [#4](https://github.com/Grupa-WSPA-3/Projekt/issues/4) | proces P-00 AS-IS | walidacja z #8 |
| [#5](https://github.com/Grupa-WSPA-3/Projekt/issues/5) | proces P-01 TO-BE — zapis | uwzględnia Q-02 (#14), Q-09 (#18), Q-13 (#19) |
| [#6](https://github.com/Grupa-WSPA-3/Projekt/issues/6) | proces P-02 TO-BE — terminy wykładowcy | uwzględnia Q-04 (#16), Q-06 (#17), Q-13 (#19), Q-11 (#20) |
| [#7](https://github.com/Grupa-WSPA-3/Projekt/issues/7) | proces P-03 TO-BE — anulowanie zapisu | zależy od decyzji Q-03 (#15) |
| [#8](https://github.com/Grupa-WSPA-3/Projekt/issues/8) | weryfikacja potrzeb i wymagań po wywiadzie | punkt koordynujący pytania Q-01…Q-10 |
| [#14–#25](https://github.com/Grupa-WSPA-3/Projekt/issues?q=is%3Aissue) | pytania i kwestie M1 | odpowiedzi mogą aktualizować FR/BR, procesy i macierz |
| [#31](https://github.com/Grupa-WSPA-3/Projekt/issues/31) | C4 L1/L2, wpływ NFR, ADR-002/003 | architektura ogólna |
| [#32](https://github.com/Grupa-WSPA-3/Projekt/issues/32) | konfiguracja GitHub Projects M1–M3 i zależności | organizacja backlogu |
| [#33](https://github.com/Grupa-WSPA-3/Projekt/issues/33) | mapowanie aktorów → US → kandydaci UC | bazuje na US-01…US-07 |
| [#34](https://github.com/Grupa-WSPA-3/Projekt/issues/34) | użycie szablonów Issues i Pull Requests | wymaga rzeczywistego PR utworzonego z szablonu |

## M2 — Projekt techniczny

**Cel:** doprecyzować decyzje zależne od środowiska i uzgodnień organizacyjnych.

| Issue | Zadanie | Powiązanie / zależność |
|---|---|---|
| [#26](https://github.com/Grupa-WSPA-3/Projekt/issues/26) | Q-12 — przyszła integracja z SSO lub planem zajęć | integracje pozostają poza v1 do czasu decyzji o zmianie zakresu |
| [#27](https://github.com/Grupa-WSPA-3/Projekt/issues/27) | Q-14 — rejestrowanie obecności / faktu konsultacji | może zmienić FR, model danych i P-02 |
| [#31](https://github.com/Grupa-WSPA-3/Projekt/issues/31) | dalsze doprecyzowanie kontenerów i wdrożenia | potwierdzenie środowiska, hostingu, kopii i protokołów |

## M3 — Projekt kompletny

**Cel:** backlog implementacji i weryfikacji. Nie oznacza, że implementacja została już wykonana.

| Issue | Zadanie | Powiązanie / zależność |
|---|---|---|
| [#35](https://github.com/Grupa-WSPA-3/Projekt/issues/35) | backlog implementacji i testów SKW | bazuje na zaakceptowanych wymaganiach, procesach i architekturze |

Przed realizacją #35 rozbić zadanie na mniejsze Issues: konta i role, terminy, wyszukiwanie, zapis, anulowanie, kontrola uprawnień oraz testy współbieżności, kompatybilności i responsywności.

## Zależności i przepływ między zadaniami

| Zadanie wynikowe | Wymaga / powiązane Issue | Dlaczego |
|---|---|---|
| P-00 AS-IS (#4) | #8 — walidacja potrzeb i wymagań | potwierdzenie obecnego przebiegu procesu |
| P-01 — zapis (#5) | #14, #18, #19 | limit miejsc, kolizje i szczegóły terminu mogą zmienić reguły zapisu |
| P-02 — terminy (#6) | #16, #17, #19, #20 | edycja, widoczność list, dane terminu i retencja |
| P-03 — anulowanie (#7) | #15 | termin graniczny anulowania |
| Architektura i ADR (#31) | FR/NFR/BR oraz zakres IN/OUT | architektura ma realizować aktualny zakres |
| Przypadki użycia (#33) | US-01…US-07 | każdy cel aktora ma kandydata UC |
| Backlog implementacji (#35) | zatwierdzone rezultaty M1/M2 | nie planować budowy na podstawie nierozstrzygniętych założeń |

## Zasady relacji

- Parent / Sub-issue oznacza rozbicie większego rezultatu na mniejsze zadania.
- „Blocked by” oznacza rzeczywistą blokadę; samo powiązanie tematyczne nie wystarcza.
- Issue może być powiązane z kilkoma wymaganiami / procesami, ale ma jednego głównego właściciela.
- Nie zamykać pytania do klienta tylko dlatego, że dodano założenie robocze.
- W każdym PR aktualizować powiązane dokumenty i macierz śledzenia.

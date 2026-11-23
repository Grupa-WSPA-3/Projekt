# Rejestr ryzyk projektu SKW

**Wersja pakietu:** M1 / 0.5  
**Przegląd:** na każdym kamieniu milowym M1, M2 i M3 oraz po istotnej zmianie zakresu.  
**Oceny:** jakościowa ocena zespołu, nie wynik pomiarów.

## Skala

- **P — prawdopodobieństwo:** 1 niskie, 2 średnie, 3 wysokie.
- **S — skutek:** 1 mały, 2 średni, 3 duży.
- **Ocena:** P × S. Wynik 6–9 jest wysoki i wymaga zaplanowanej reakcji oraz powiązanego Issue.
- **Rodzaj projektowy:** ryzyko pracy zespołu lub realizacji projektu.
- **Rodzaj produktowy:** ryzyko działania, bezpieczeństwa, jakości lub otoczenia systemu.

## Rejestr

| ID | Rodzaj | Zdarzenie ryzykowne | Przyczyna | P | S | P×S | Reakcja (strategia i działanie) | Właściciel | Status | Powiązane Issue |
|---|---|---|---|---:|---:|---:|---|---|---|---|
| R-01 | projektowe | Brak potwierdzonych danych wywiadu spowoduje, że potrzeby i AS-IS pozostaną hipotezami. | Nie ma kompletnego, potwierdzonego protokołu z odpowiedziami klienta. | 3 | 3 | **9** | **Ograniczanie:** uzupełnić protokół wyłącznie z rzeczywistych notatek; oznaczać hipotezy; nie zamykać walidacji bez dowodu. | @mtwspa | otwarte | [#8](https://github.com/Grupa-WSPA-3/Projekt/issues/8) |
| R-02 | produktowe | Dwie równoczesne próby mogą zająć ostatnie miejsce i przekroczyć limit konsultacji. | Kontrola wyłącznie na podstawie wcześniejszego podglądu nie jest atomowa. | 2 | 3 | **6** | **Ograniczanie:** transakcja w backendzie, ograniczenia integralności bazy i testy współbieżności dla 100 powtórzeń. | @Hryak123 | otwarte | [#5](https://github.com/Grupa-WSPA-3/Projekt/issues/5) |
| R-03 | produktowe | Niejasna reguła anulowania lub edycji terminu może spowodować niespójne statusy zapisów. | Graniczny czas anulowania i zasady edycji terminu z aktywnymi zapisami wymagają potwierdzenia. | 3 | 2 | **6** | **Ograniczanie:** rozstrzygnąć Q-03 i Q-04; zaktualizować FR-10/FR-12, BR-05/BR-07 i P-02/P-03. | @mtwspa | otwarte | [#15](https://github.com/Grupa-WSPA-3/Projekt/issues/15), [#16](https://github.com/Grupa-WSPA-3/Projekt/issues/16) |
| R-04 | projektowe | Rozszerzanie v1 o SSO, pocztę, plan zajęć lub wideokonferencje opóźni M1 i zwiększy zakres. | Propozycje integracji mogą być mylone z potwierdzonymi potrzebami. | 2 | 3 | **6** | **Unikanie:** utrzymać OUT dla v1; każdą nową integrację poprzedzić pytaniem, oceną make-or-buy i zmianą zakresu. | @mtwspa | monitorowane | [#26](https://github.com/Grupa-WSPA-3/Projekt/issues/26), [#2](https://github.com/Grupa-WSPA-3/Projekt/issues/2) |
| R-05 | produktowe | Osoba bez uprawnienia uzyska dostęp do listy studentów lub danych zapisu. | Brak kontroli właściciela zasobu albo nadmierne uprawnienia administratora. | 2 | 3 | **6** | **Ograniczanie:** autoryzacja w backendzie, minimalizacja danych, testy negatywne trzech ról, rozstrzygnięcie zakresu administratora. | @semenukalina89-maker | otwarte | [#17](https://github.com/Grupa-WSPA-3/Projekt/issues/17) |
| R-06 | projektowe | Wymagania, procesy, ADR i macierz rozjadą się po zmianie pojedynczego artefaktu. | Powiązane pliki mogą być edytowane w różnym czasie przez różne osoby. | 2 | 2 | 4 | **Ograniczanie:** zmiany pokrewnych artefaktów w jednym PR; kontrola ID i macierzy w Definition of Done. | @miumeowww | monitorowane | [#3](https://github.com/Grupa-WSPA-3/Projekt/issues/3) |
| R-07 | projektowe | Członkowie zespołu inaczej zinterpretują „termin”, „zapis”, „aktywność” lub „anulowanie”. | Niepełna synchronizacja nazewnictwa w opisach i interfejsie. | 2 | 2 | 4 | **Ograniczanie:** używać kanonicznych definicji słownika; zmiany pojęć przeglądać razem z FR i procesami. | @miumeowww | monitorowane | [#3](https://github.com/Grupa-WSPA-3/Projekt/issues/3) |
| R-08 | projektowe | Zadanie bez właściciela, kryterium lub statusu zostanie pominięte albo wykonane podwójnie. | Brak aktualnej tablicy i niejednolite użycie Issues / Projects. | 2 | 3 | **6** | **Ograniczanie:** jedna pozycja Issue na zadanie, jeden właściciel, kryteria akceptacji i widoki M1–M3; cotygodniowy przegląd backlogu. | @mtwspa | otwarte | [#3](https://github.com/Grupa-WSPA-3/Projekt/issues/3), [#32](https://github.com/Grupa-WSPA-3/Projekt/issues/32) |
| R-09 | produktowe | Przyjęte progi wydajności okażą się nieadekwatne do rzeczywistego środowiska. | Profil 5 000 terminów i 50 równoczesnych użytkowników jest założeniem projektowym, nie pomiarem uczelni. | 2 | 2 | 4 | **Akceptacja i monitorowanie:** potwierdzić profil obciążenia przed testem; zmienić NFR, jeśli dane uczelni będą inne. | @Hryak123 | monitorowane | [#31](https://github.com/Grupa-WSPA-3/Projekt/issues/31) |
| R-10 | projektowe | Brak wzajemnych recenzji i rozpoznawalnego wkładu utrudni ocenę jakości oraz pracy zespołu. | Zmiany mogą trafiać do głównej gałęzi bez przejrzenia przez inną osobę. | 2 | 2 | 4 | **Ograniczanie:** stosować PR template, wymagać recenzenta innego niż autor, dzielić zadania między członków zespołu. | @mtwspa | otwarte | [#34](https://github.com/Grupa-WSPA-3/Projekt/issues/34) |
| R-11 | produktowe | Nieustalony sposób tworzenia kont i odzyskiwania dostępu doprowadzi do niezgodnego modelu logowania. | Q-05 nie rozstrzyga, kto zakłada konto ani jaki mechanizm będzie dostępny. | 2 | 3 | **6** | **Ograniczanie:** nie zakładać integracji SSO; rozstrzygnąć Q-05 przed wyborem mechanizmu; wydzielić kontrolę ról od dostawcy tożsamości. | @Hryak123 | otwarte | [#22](https://github.com/Grupa-WSPA-3/Projekt/issues/22) |
| R-12 | produktowe | Wybrane rozwiązanie nie będzie możliwe do wdrożenia lub odtworzenia w środowisku uczelni. | Hosting, baza, kopie i obowiązki administratora nie zostały potwierdzone. | 2 | 2 | 4 | **Ograniczanie:** potwierdzić środowisko i wymagania operacyjne przed zamrożeniem technologii; opisać kopie i odtwarzanie w modelu wdrożenia. | @Hryak123 | otwarte | [#31](https://github.com/Grupa-WSPA-3/Projekt/issues/31) |

## Podsumowanie

- Ryzyka projektowe: R-01, R-04, R-06, R-07, R-08, R-10.
- Ryzyka produktowe: R-02, R-03, R-05, R-09, R-11, R-12.
- Wysoka ocena (6–9): R-01, R-02, R-03, R-04, R-05, R-08, R-11. Dla każdego wskazano powiązane Issue.
- Status „zamknięte” wymaga dowodu: odpowiedzi, decyzji, testu, PR lub innego artefaktu.

## Strategie reakcji

| Strategia | Znaczenie | Przykład dla SKW |
|---|---|---|
| Unikanie | zmiana zakresu / planu usuwa ryzyko | brak integracji SSO i planu zajęć w v1 |
| Ograniczanie | zmniejszenie prawdopodobieństwa lub skutku | transakcje, testy, kontrola ról i wcześniejsze potwierdzenie wymagań |
| Przeniesienie | uzgodnienie odpowiedzialności z inną stroną | wymagania dostępności hostingu ustalone z administratorem uczelni |
| Akceptacja | świadome przyjęcie niewielkiego ryzyka i monitorowanie | utrzymanie roboczego profilu obciążenia do czasu potwierdzenia |

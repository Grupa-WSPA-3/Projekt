# P-03 — Anulowanie własnego zapisu przez studenta (TO-BE)

**Wersja:** 0.1 — proces pomocniczy  
**Właściciel procesu:** Sofiia Vetvytska  
**Uczestnicy / tory:** Student, System SKW  
**Cel:** umożliwić studentowi zwolnienie miejsca poprzez anulowanie własnego aktywnego zapisu.

## Zdarzenie początkowe

Student nie może lub nie chce uczestniczyć w konsultacji, na którą jest zapisany.

## Kroki

| Krok | Tor | Czynność | Typ | Wymagania / reguły |
|---|---|---|---|---|
| P-03.1 | Student | otwiera listę własnych zapisów i wybiera zapis do anulowania | zadanie użytkownika | FR-10, FR-16 |
| P-03.2 | System SKW | pobiera zapis i sprawdza, czy należy do zalogowanego studenta | zadanie usługi | FR-02, BR-04 |
| P-03.3 | System SKW | sprawdza, czy zapis ma status aktywny | zadanie usługi | FR-10, BR-07 |
| P-03.4 | System SKW | sprawdza warunek czasowy anulowania, jeśli zostanie przyjęty | zadanie usługi | Q-03 — reguła do rozstrzygnięcia |
| P-03.5 | Student | potwierdza zamiar anulowania | zadanie użytkownika | FR-10 |
| P-03.6 | System SKW | zmienia status zapisu na Anulowany, zwalnia miejsce i prezentuje rezultat | zadanie usługi | FR-10, FR-16, FR-17, BR-07 |

## Bramki / ścieżki alternatywne

| Bramka | Pytanie | TAK | NIE |
|---|---|---|---|
| G-01 | Czy zapis należy do zalogowanego studenta? | kontynuuj | odmów dostępu, bez zmiany danych |
| G-02 | Czy zapis jest aktywny? | kontynuuj | poinformuj, że zapis jest już anulowany / nieaktywny |
| G-03 | Czy anulowanie mieści się w dopuszczalnym czasie? | kontynuuj | odmów, jeżeli zespół przyjmie limit czasowy; obecnie Q-03 otwarte |

## Wyniki

- zapis anulowany, miejsce zwolnione, status widoczny studentowi;
- operacja odrzucona — zapis nie należy do studenta;
- operacja odrzucona — zapis jest już anulowany;
- operacja odrzucona z powodu reguły czasowej, jeśli zostanie zatwierdzona.

## Założenia i pytania

Nie przyjmujemy konkretnego terminu granicznego anulowania bez odpowiedzi na Q-03. W wersji roboczej proces pozwala anulować aktywny własny zapis, a warunek czasowy traktuje jako opcjonalną bramkę zależną od decyzji. Nie wolno przedstawiać nieustalonego limitu jako zatwierdzonej reguły.


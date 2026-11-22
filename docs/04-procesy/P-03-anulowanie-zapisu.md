# P-03 — Anulowanie własnego zapisu przez studenta (TO-BE)

**Wersja:** 0.2 — proces pomocniczy  
**Właściciel procesu:** Sofiia Vetvytska  
**Pula BPMN (opis logiczny):** Uczelnia · **Tory:** Student, System SKW

## Cel procesu

Umożliwić studentowi anulowanie własnego aktywnego zapisu, zwolnienie miejsca i otrzymanie jednoznacznego statusu operacji.

## Wyzwalacz i warunki

**Zdarzenie początkowe:** Student nie może lub nie chce uczestniczyć w konsultacji, na którą jest zapisany.

**Warunki wstępne:** student jest zalogowany; system weryfikuje, czy zapis należy do tego studenta (FR-01, FR-02, BR-04).

## Kroki procesu

| Krok | Tor | Typ zadania | Czynność biznesowa | Wymagania / reguły |
|---|---|---|---|---|
| P-03.1 | Student | użytkownika | wybiera własny zapis do anulowania | FR-10, FR-16 |
| P-03.2 | System SKW | usługi | sprawdza rolę i właściciela zapisu | FR-02, BR-04 |
| P-03.3 | System SKW | usługi | sprawdza, czy zapis ma status Aktywny | FR-10, BR-07 |
| P-03.4 | System SKW | usługi | sprawdza regułę czasu granicznego, jeśli zostanie uzgodniona | Q-03 — nierozstrzygnięte |
| P-03.5 | Student | użytkownika | potwierdza zamiar anulowania własnego zapisu | FR-10 |
| P-03.6 | System SKW | usługi | zmienia status na Anulowany, zwalnia miejsce i prezentuje wynik | FR-10, FR-16, FR-17, BR-07 |

## Bramki / alternatywy

| Bramka | Pytanie | TAK | NIE |
|---|---|---|---|
| G-01 | Czy zapis należy do zalogowanego studenta? | kontynuuj | odmów dostępu; status bez zmian |
| G-02 | Czy zapis jest aktywny? | kontynuuj | pokaż informację, że zapis jest już nieaktywny |
| G-03 | Czy anulowanie mieści się w dopuszczalnym czasie? | kontynuuj | odmów, jeżeli zostanie zatwierdzony limit czasowy; Q-03 pozostaje otwarte |

## Wyniki

- zapis anulowany, miejsce zwolnione, status widoczny studentowi;
- odmowa — zapis nie należy do studenta;
- odmowa — zapis jest już anulowany / nieaktywny;
- odmowa — upłynął termin anulowania, jeżeli taka reguła zostanie przyjęta.

## Otwarte kwestie 

Graniczny czas anulowania nie został ustalony. Nie wpisujemy konkretnej liczby godzin ani dni bez odpowiedzi na Q-03. W obecnej wersji opisujemy anulowanie aktywnego własnego zapisu, a ograniczenie czasowe traktujemy jako warunkowe.

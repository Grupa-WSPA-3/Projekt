# P-01 — Przeglądanie i zapis na konsultację (TO-BE)

**Wersja:** 0.1 · **Właściciel:** @Hryak123 · **Issue:** [#5](https://github.com/Grupa-WSPA-3/Projekt/issues/5) · **Powiązane:** P-00 (AS-IS), FR-01…FR-09, FR-16…FR-18, BR-02, BR-03, BR-09

## Cel procesu
Umożliwić studentowi znalezienie przyszłego terminu konsultacji i utworzenie jednego aktywnego zapisu, o ile termin jest dostępny i student ma odpowiednie uprawnienia.

## Wyzwalacz
Student chce znaleźć i zarezerwować termin konsultacji.

## Uczestnicy (tory)
- **Student** — loguje się, przegląda terminy, wybiera termin i potwierdza zapis.
- **System SKW** — udostępnia terminy, sprawdza warunki zapisu, zapisuje wynik i pokazuje status.

## Wyniki (zdarzenia końcowe)
- zapis utworzony i potwierdzony;
- brak dostępu / nieprawidłowa rola;
- termin niedostępny (przeszły, anulowany lub bez wolnych miejsc);
- student ma już aktywny zapis na ten termin.

## Diagram BPMN 2.0

![P-01 — przeglądanie i zapis na konsultację](P-01-rezerwacja-konsultacji.svg)

Źródło: [P-01-rezerwacja-konsultacji.bpmn](P-01-rezerwacja-konsultacji.bpmn).

## Kroki

| Krok | Tor | Typ zadania / elementu | Opis | Wymagania |
|---|---|---|---|---|
| P-01.1 | Student | użytkownika | Zaloguj się do SKW | FR-01 |
| P-01.2 | System SKW | bramka XOR / decyzja | Sprawdź, czy użytkownik ma rolę Student | FR-02, BR-09 |
| P-01.3 | Student | użytkownika | Przeglądaj przyszłe terminy konsultacji | FR-03 |
| P-01.4 | Student | użytkownika | Filtruj listę terminów według wykładowcy lub daty | FR-04, FR-05 |
| P-01.5 | Student | użytkownika | Otwórz szczegóły wybranego terminu | FR-06 |
| P-01.6 | Student | użytkownika | Zatwierdź zapis na wybrany termin | FR-07 |
| P-01.7 | System SKW | usługi | Sprawdź status terminu, limit miejsc i istnienie aktywnego zapisu studenta | FR-08, FR-09, FR-18; BR-02, BR-03 |
| P-01.8 | System SKW | usługi | Utwórz aktywny zapis | FR-07, FR-08, FR-09 |
| P-01.9 | System SKW | usługi | Wyświetl wynik operacji i aktualny status zapisu | FR-16, FR-17 |
## Wyjątki i ścieżki alternatywne

| Wyjątek | Gdzie | Reakcja | Wymaganie / BR |
|---|---|---|---|
| Użytkownik nie jest zalogowany lub nie ma roli Student | P-01.1–P-01.2 | Zakończ proces odmową dostępu; nie zmieniaj danych | FR-01, FR-02, BR-09 |
| Termin jest przeszły, anulowany albo nie ma wolnych miejsc | P-01.7 | Nie twórz zapisu; pokaż przyczynę | FR-03, FR-08, FR-18, BR-02 |
| Student ma już aktywny zapis na ten termin | P-01.7 | Odrzuć próbę bez tworzenia duplikatu | FR-09, BR-03 |
| Dwie osoby próbują zająć ostatnie miejsce jednocześnie | P-01.7–P-01.8 | Tylko jedna operacja może zakończyć się aktywnym zapisem | FR-08, NFR-05, BR-02 |

## Powiązanie z AS-IS

P-01 zastępuje przede wszystkim kroki P-00.1–P-00.4: ręczne wyszukiwanie informacji o konsultacjach, kontakt studenta z wykładowcą oraz uzgadnianie dogodnego terminu. W SKW student przegląda wspólną listę przyszłych terminów, sprawdza szczegóły i samodzielnie inicjuje zapis; system weryfikuje dostępność i potwierdza wynik. Integracja z planem zajęć uczelni pozostaje poza zakresem v1.

## Otwarte pytania
- Czy limit miejsc może być większy niż 1? ([Q-02](https://github.com/Grupa-WSPA-3/Projekt/issues/14))
- Czy student może mieć dwa zapisy na nakładające się terminy u różnych wykładowców? ([Q-09](https://github.com/Grupa-WSPA-3/Projekt/issues/18))
- Jakie pola szczegółów terminu są obowiązkowe? ([Q-13](https://github.com/Grupa-WSPA-3/Projekt/issues/19))

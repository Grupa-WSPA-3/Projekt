# P-00 — Obecna organizacja konsultacji (AS-IS)

**Wersja:** 0.1 · **Właściciel:** @mtwspa · **Powiązane:** karta projektu, N-01…N-07

> **Status źródłowy:** rekonstrukcja robocza na podstawie istniejących notatek zespołu. Nie jest to wynik udokumentowanej obserwacji ani rzeczywistego wywiadu. Kanały komunikacji i sposób prowadzenia listy wymagają potwierdzenia.

## Cel procesu
Opisać, w jaki sposób student obecnie uzyskuje informację o konsultacji i uzgadnia termin z wykładowcą przed wdrożeniem SKW.

## Wyzwalacz
Student potrzebuje konsultacji z wykładowcą.

## Uczestnicy
- **Student** — poszukuje informacji i kontaktuje się z wykładowcą.
- **Wykładowca** — odpowiada na prośbę i uzgadnia możliwy termin.
- **Kanały komunikacji / własna lista** — sposób ewidencji do ustalenia w wywiadzie; nie są częścią SKW.

## Wyniki
- termin konsultacji uzgodniony;
- student nie uzgadnia terminu lub rezygnuje;
- termin zostaje później zmieniony albo odwołany — sposób informowania wymaga weryfikacji.

## Diagram
![P-00 — obecna organizacja konsultacji](P-00-rezerwacja-as-is.svg)

Źródło: [P-00-rezerwacja-as-is.bpmn](P-00-rezerwacja-as-is.bpmn).

## Kroki

| Krok | Rola | Czynność | Dokument / narzędzie | Punkt bólu / powiązanie |
|---|---|---|---|---|
| P-00.1 | Student | Poszukaj informacji o konsultacjach | Strona przedmiotu, wiadomości lub informacja ustna — do potwierdzenia | Informacje mogą być rozproszone (N-01) |
| P-00.2 | Student | Skontaktuj się z wykładowcą | E-mail, komunikator lub rozmowa — do potwierdzenia | Ręczne uzgadnianie terminu (N-01, N-02) |
| P-00.3 | Wykładowca | Przedstaw możliwy termin | Odpowiedź w używanym kanale | Brak wspólnego, aktualnego widoku dostępności (N-01) |
| P-00.4 | Student i wykładowca | Uzgodnij i potwierdź termin | Wiadomość lub rozmowa — do potwierdzenia | Możliwa wielokrotna wymiana wiadomości (N-02) |
| P-00.5 | Wykładowca | Prowadź informację o zapisanych osobach | Lista, skrzynka lub inny sposób — do ustalenia | Aktualność listy wymaga weryfikacji (N-07) |
| P-00.6 | Student lub wykładowca | Poinformuj o rezygnacji albo zmianie terminu | Kanał komunikacji do ustalenia | Informacja o zmianie może nie dotrzeć do wszystkich (N-05, N-06, N-10) |

## Wyjątki i ścieżki alternatywne

| Sytuacja | Gdzie | Obecna reakcja | Status |
|---|---|---|---|
| Brak odpowiedzi wykładowcy | P-00.2–P-00.3 | Sposób ponawiania kontaktu nie jest opisany | Pytanie do wywiadu |
| Brak dogodnego terminu | P-00.3–P-00.4 | Dalsze uzgadnianie lub rezygnacja | Hipoteza do walidacji |
| Zmiana lub odwołanie konsultacji | P-00.6 | Kontakt z zainteresowanymi osobami | Hipoteza do walidacji |

## Punkty bólu do sprawdzenia
1. Informacje o konsultacjach mogą być rozproszone.
2. Uzgadnianie terminów może wymagać ręcznej wymiany wiadomości.
3. Wykładowca może prowadzić listę zapisów poza wspólnym systemem.
4. Zmiany i rezygnacje mogą wymagać ponownego kontaktu.

Każdy punkt jest hipotezą wynikającą z notatek zespołu; należy go potwierdzić lub poprawić po wywiadzie.

## Zmiany względem AS-IS
Nie dotyczy — P-00 opisuje stan obecny i stanowi punkt odniesienia dla P-01–P-03.

## Otwarte pytania
- Jak student faktycznie znajduje informacje o konsultacjach?
- Jakim kanałem student kontaktuje się z wykładowcą?
- Gdzie i przez kogo prowadzona jest lista zapisów?
- Jak wygląda anulowanie zapisu i odwołanie całego terminu?

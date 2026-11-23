# Przypadki użycia — aktorzy, historyjki i kandydaci UC

**Wersja pakietu:** M1 / 0.5  
**Status:** katalog kandydatów wyprowadzonych z historyjek US-01…US-07 i wymagań FR.

## Aktorzy

| Aktor | Odpowiedzialność | Historyjki |
|---|---|---|
| Student | przegląda konsultacje, wyszukuje terminy, zapisuje się i anuluje własny zapis | US-01, US-02, US-03, US-04 |
| Wykładowca | zarządza własnymi terminami i przegląda listy zapisów | US-01, US-05, US-06 |
| Administrator | zarządza aktywnością kont i przypisaniem ról | US-01, US-07 |

## Mapowanie aktor → historyjka → kandydat UC

| Aktor | Historyjka | Cel użytkownika | Kandydaci UC | Powiązane FR |
|---|---|---|---|---|
| Student | US-01 | zalogować się i korzystać z funkcji roli | UC-01 — Zaloguj się | FR-01, FR-02 |
| Student | US-02 | znaleźć przyszłą konsultację i sprawdzić szczegóły | UC-02 — Przeglądaj dostępne konsultacje; UC-03 — Wyszukaj konsultacje; UC-04 — Wyświetl szczegóły terminu | FR-03…FR-06 |
| Student | US-03 | zarezerwować dostępne miejsce | UC-05 — Zapisz się na konsultację | FR-07, FR-08, FR-09, FR-17, FR-18 |
| Student | US-04 | anulować własny zapis | UC-06 — Anuluj własny zapis | FR-10, FR-16 |
| Wykładowca | US-01 | zalogować się i korzystać z funkcji roli | UC-01 — Zaloguj się | FR-01, FR-02 |
| Wykładowca | US-05 | zarządzać własnymi terminami | UC-07 — Utwórz termin; UC-08 — Edytuj termin; UC-09 — Anuluj termin | FR-11, FR-12, FR-14, FR-16 |
| Wykładowca | US-06 | przygotować się do konsultacji, przeglądając zapisy | UC-10 — Wyświetl listę zapisów | FR-13 |
| Administrator | US-01 | zalogować się i korzystać z funkcji roli | UC-01 — Zaloguj się | FR-01, FR-02 |
| Administrator | US-07 | zarządzać kontami i rolami | UC-11 — Zarządzaj kontami i rolami | FR-15 |

## Katalog kandydatów przypadków użycia

| ID | Przypadek użycia | Aktor główny | Powiązane FR | Proces |
|---|---|---|---|---|
| UC-01 | Zaloguj się | Student / Wykładowca / Administrator | FR-01, FR-02 | P-01, P-02, P-03 |
| UC-02 | Przeglądaj dostępne konsultacje | Student | FR-03 | P-01 |
| UC-03 | Wyszukaj konsultacje | Student | FR-04, FR-05 | P-01 |
| UC-04 | Wyświetl szczegóły terminu | Student | FR-06 | P-01 |
| UC-05 | Zapisz się na konsultację | Student | FR-07, FR-08, FR-09, FR-17, FR-18 | P-01 |
| UC-06 | Anuluj własny zapis | Student | FR-10, FR-16 | P-03 |
| UC-07 | Utwórz termin konsultacji | Wykładowca | FR-11 | P-02 |
| UC-08 | Edytuj termin konsultacji | Wykładowca | FR-12 | P-02 |
| UC-09 | Anuluj termin konsultacji | Wykładowca | FR-14, FR-16 | P-02 |
| UC-10 | Wyświetl listę zapisów | Wykładowca | FR-13 | P-02 |
| UC-11 | Zarządzaj kontami i rolami | Administrator | FR-15 | poza P-01…P-03 |

## Scenariusz UC-05 — Zapisz się na konsultację

**Warunek wstępny:** Student jest zalogowany; istnieje przyszły i aktywny termin.  
**Wyzwalacz:** Student wybiera funkcję zapisu dla wybranego terminu.

1. Student otwiera szczegóły terminu.
2. System prezentuje datę, godzinę, wykładowcę, status i dostępność.
3. Student zatwierdza zapis.
4. Backend ponownie sprawdza status terminu, limit miejsc, rolę i aktywny zapis studenta.
5. Backend atomowo tworzy zapis, jeśli warunki są spełnione.
6. System pokazuje potwierdzenie i nowy status.

**Alternatywy:** brak miejsca, termin anulowany lub przeszły — system odmawia; istniejący aktywny zapis — system nie tworzy duplikatu; równoczesne próby — tylko jedna może zająć ostatnie miejsce.

## Pokrycie historyjek Must

| Historyjka | Must FR | Kandydaci UC |
|---|---|---|
| US-01 | FR-01, FR-02 | UC-01 |
| US-02 | FR-03 | UC-02; UC-03 i UC-04 pokrywają wymagania Should |
| US-03 | FR-07, FR-08, FR-09, FR-17 | UC-05 |
| US-04 | FR-10 | UC-06 |
| US-05 | FR-11, FR-14 | UC-07, UC-09 |
| US-06 | brak Must (Should) | UC-10 |
| US-07 | brak Must (Should) | UC-11 |

Wszystkie wymagania Must są przypisane do co najmniej jednej historyjki i kandydata UC. Pełny diagram UML przypadków użycia i scenariusze alternatywne można rozwinąć podczas dalszego modelowania.

## Zakres poza v1

Nie opisano integracji SSO, powiadomień e-mail/SMS, wideokonferencji, płatności ani rezerwacji cyklicznych, ponieważ nie należą do zakresu pierwszej wersji.

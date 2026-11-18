# Przypadki użycia — zakres wstępny SKW

**Status:** zarys wynikający z FR 0.2; pełne scenariusze UML i diagram przypadków użycia mogą zostać dopracowane na etapie modelowania.

## Aktorzy

- **Student** — przegląda konsultacje, zapisuje się i anuluje własny zapis.
- **Wykładowca** — zarządza własnymi terminami i listami zapisów.
- **Administrator** — aktywuje / dezaktywuje konta i przypisuje role.

## Katalog przypadków użycia

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

**Warunek wstępny:** student jest zalogowany; istnieje termin przyszły i aktywny.  
**Wyzwalacz:** student wybiera funkcję zapisu dla wybranego terminu.

1. Student otwiera szczegóły terminu.
2. System prezentuje datę, godzinę, wykładowcę, status i dostępność.
3. Student zatwierdza zapis.
4. System ponownie sprawdza status terminu, limit miejsc i aktywny zapis studenta.
5. System atomowo tworzy zapis, jeśli warunki są spełnione.
6. System wyświetla potwierdzenie i nowy status.

**Alternatywy:** brak miejsca / termin anulowany / termin przeszły — system odmawia; istniejący aktywny zapis — system nie tworzy duplikatu; równoczesne próby — tylko jedna może zająć ostatnie miejsce.

## Zakres poza bieżącym modelem

Nie opisano integracji z SSO, powiadomień e-mail/SMS, wideokonferencji, płatności ani rezerwacji cyklicznych, ponieważ nie należą do zakresu v1.


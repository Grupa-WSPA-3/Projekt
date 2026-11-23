# Dopasowanie oczekiwań do oferty — make / buy / use

**Pakiet:** M1 / 0.5 · **Status:** analiza i propozycje decyzji do przeglądu zespołu; nie oznacza wyboru konkretnego dostawcy ani zawarcia umowy.

## Znaczenie decyzji

| Opcja | Znaczenie |
|---|---|
| **make** | projektujemy i realizujemy własną funkcję / logikę SKW |
| **buy** | kupujemy lub subskrybujemy gotowy produkt / usługę |
| **use / reuse** | wykorzystujemy istniejącą usługę organizacji albo bibliotekę / silnik open source |

## Kryteria oceny

- **Dopasowanie:** pełne / częściowe / brak / niezweryfikowane; które FR/NFR są realizowane bez zmian?
- **Koszt:** licencja / abonament + integracja + utrzymanie. Nie wpisujemy wymyślonych kwot; aktualną cenę sprawdzamy przy wyborze produktu.
- **Ryzyko:** awaria, zmiana warunków, wycofanie produktu, bezpieczeństwo i utrzymanie.
- **Zależność od dostawcy:** eksport danych i możliwość zastąpienia usługi.
- **RODO:** lokalizacja danych, dostęp, umowa powierzenia, przetwarzanie poza EOG.
- **Czas:** własna realizacja vs integracja gotowego rozwiązania.

## Ocena obszarów

| Obszar | Wymagania | Opcje | Dopasowanie | Koszt | Ryzyko / zależność | RODO / dane | Czas | Decyzja |
|---|---|---|---|---|---|---|---|---|
| Rdzeń SKW: terminy, dostępność, zapisy i anulowanie | FR-03…FR-18, BR-01…BR-10, NFR-05…NFR-07 | gotowy SaaS rezerwacyjny vs własna logika | SaaS — częściowe / niezweryfikowane; musi obsłużyć role, własność terminów, limity i statusy | oferta i koszt integracji niepotwierdzone; własna realizacja wymaga pracy zespołu | wysoka zależność i możliwe ograniczenia eksportu / reguł | dane studentów wymagają kontroli dostępu; przed SaaS konieczna ocena przetwarzania | gotowy kalendarz może być szybszy, dopasowanie może wydłużyć prace | **MAKE** — własny rdzeń; ADR-003 |
| Uwierzytelnianie, role i kontrola własności | FR-01, FR-02, FR-15; NFR-06; Q-05 | biblioteka bezpieczeństwa / mechanizmy frameworka; SSO jako możliwość przyszła | biblioteka wspiera sesję; model kont pozostaje nieustalony | koszt licencji do sprawdzenia; nie zakładamy dostawcy SaaS | ryzyko konfiguracji i utrzymania biblioteki; SSO poza v1 | nie wysyłać danych kont do usługi SaaS bez oceny; minimalizować dane | sprawdzona biblioteka krótsza niż własna kryptografia | **USE** biblioteki po przeglądzie; role i własność — **MAKE**; sposób kont pozostaje Q-05 |
| Silnik bazy danych | FR-07…FR-16, BR-02/03/07; NFR-02/05/07 | silnik relacyjny open source, np. PostgreSQL, vs własny magazyn danych | relacyjna baza pasuje do relacji termin–zapis, transakcji i ograniczeń | brak opłaty za silnik nie oznacza braku kosztu serwera, kopii i administracji | ryzyko operacyjne: kopie, aktualizacje i odtwarzanie; SQL / eksport ogranicza zależność | dane pod kontrolą organizacji przy hostingu w zatwierdzonym środowisku | użycie gotowego silnika krótsze niż tworzenie własnego | **USE** silnika relacyjnego; PostgreSQL — kandydat do potwierdzenia |
| Filtrowanie dat i widok terminów | FR-03…FR-06; NFR-04/08 | własne filtry vs biblioteka komponentu daty / kalendarza | prosty filtr pasuje; rozbudowany kalendarz nie jest wymagany v1 | koszt biblioteki zależy od licencji; sprawdzić ją przed wyborem | ryzyko nieaktywnego komponentu i braku dostępności klawiaturą | dane terminów pozostają w SKW; nie wysyłać ich do zewnętrznego kalendarza | mała biblioteka może skrócić UI; prosty filtr można zbudować bez niej | **USE** tylko po sprawdzeniu licencji, utrzymania i dostępności |
| Automatyczne powiadomienia e-mail/SMS | brak wymagania w v1; OUT | SMTP uczelni vs zewnętrzna usługa | nie dotyczy v1; potrzeba i kanał niezatwierdzone | brak kosztu w v1; przyszłą ofertę sprawdzić | zależność od limitów, SLA i dostępności | wiadomości mogą zawierać dane osobowe; przed usługą zewnętrzną ocena umowy i lokalizacji | wdrożenie teraz zwiększyłoby zakres bez potwierdzonej potrzeby | **WON'T NOW**; wrócić po zmianie zakresu |
| Repozytorium, Issues i backlog | organizacja pracy, nie funkcja dla studentów | istniejące GitHub Issues + Projects vs osobna tablica | pasuje do śledzenia dokumentów, właścicieli i PR | nie wprowadza się dodatkowego narzędzia; warunki platformy zależą od kont | zależność od GitHub; dokumenty są w repozytorium | nie umieszczać w Issues danych osobowych studentów | wykorzystanie istniejącej platformy jest najszybsze | **USE** GitHub |

## Wymagania, których nie przejmuje gotowy produkt

Zespół nadal projektuje:
- atomowe sprawdzenie limitu miejsca przy zatwierdzeniu zapisu (FR-08, BR-02, BR-10);
- ochronę przed drugim aktywnym zapisem (FR-09, BR-03);
- kontrolę roli i własności zasobu (FR-02, BR-04);
- status anulowania zapisu i terminu (FR-10, FR-14, FR-16);
- procesy P-01, P-02 i P-03.

## Otwarte decyzje i warunki przed zakupem

1. Sposób tworzenia kont i odzyskiwania dostępu pozostaje Q-05; SSO nie jest decyzją v1.
2. Integracja z planem zajęć / SSO pozostaje poza v1 i jest przedmiotem Q-12 (#26).
3. Przed biblioteką UI sprawdzić licencję, utrzymanie i dostępność.
4. Przed wyborem hostingu potwierdzić wymagania uczelni, kopie zapasowe, retencję i lokalizację danych.
5. Kosztu dostawcy nie szacować bez aktualnej oferty.

## Powiązane decyzje

- [ADR-002 — Modularny monolit](../adr/ADR-002-styl-architektury.md)
- [ADR-003 — Rdzeń domenowy SKW: MAKE](../adr/ADR-003-rdzen-skw-make.md)

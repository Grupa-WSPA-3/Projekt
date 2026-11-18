# Wymagania — System obsługi konsultacji wykładowców (SKW)

**Wersja:** 0.1 — wstępna specyfikacja do walidacji  
**Autorzy:** zespół SKW  
**Status:** do przeglądu zespołu i weryfikacji na podstawie wywiadu z klientem.

> **Źródła:** protokół wywiadu nie zawiera jeszcze zweryfikowanych odpowiedzi ani cytatów. Potrzeby N-xx i wynikające z nich wymagania są wstępnymi hipotezami zespołu, opartymi na karcie projektu. Po rozmowie z klientem należy uzupełnić źródła, skorygować treść i zachować identyfikatory tam, gdzie znaczenie pozostaje bez zmian.

## 1. Potrzeby

| ID | Potrzeba (językiem klienta) | Typ | Kto zgłosił / rola | Źródło |
|---|---|---|---|---|
| N-01 | Student chce znaleźć aktualne przyszłe terminy konsultacji w jednym miejscu. | potrzeba (hipoteza) | Student (rola zakładana) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-02 | Student chce wyszukać konsultacje według wykładowcy i terminu. | żądanie funkcjonalne (hipoteza) | Student (rola zakładana) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-03 | Student potrzebuje informacji wystarczających do wyboru konsultacji. | potrzeba (hipoteza) | Student (rola zakładana) | Karta projektu 0.3 — pola do potwierdzenia wywiadem |
| N-04 | Student chce zapisać się na dostępne miejsce bez ryzyka, że limit zostanie przekroczony. | żądanie (hipoteza) | Student / wykładowca (role zakładane) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-05 | Student chce anulować własny zapis bez kontaktu z wykładowcą. | potrzeba (hipoteza) | Student (rola zakładana) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-06 | Wykładowca chce sam tworzyć, edytować i odwoływać własne terminy. | potrzeba (hipoteza) | Wykładowca (rola zakładana) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-07 | Wykładowca chce sprawdzić listę studentów zapisanych na jego konsultację. | żądanie funkcjonalne (hipoteza) | Wykładowca (rola zakładana) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-08 | Administrator potrzebuje możliwości zarządzania kontami i rolami. | potrzeba (hipoteza) | Administrator (rola zakładana) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-09 | Użytkownik potrzebuje dostępu do czynności i danych odpowiednich dla swojej roli. | potrzeba (hipoteza) | Student / wykładowca / administrator (role zakładane) | Karta projektu 0.3 — założenie zespołu; do potwierdzenia wywiadem |
| N-10 | Użytkownik potrzebuje jasnej informacji o wyniku zapisu lub anulowania. | potrzeba projektowa (hipoteza) | Student / wykładowca (role zakładane) | Wniosek zespołu; hipoteza do potwierdzenia wywiadem |

## 2. Wymagania funkcjonalne (FR)

Priorytety wynikają z wartości dla użytkownika na pierwszą wersję. „Must” stanowi 10 z 18 FR (55,6%), czyli mniej niż zalecane około 60%.
    
| ID | Treść wymagania | Źródło | Kryterium / uwagi |
| --- | --- | --- | --- |
| FR-01 | System umożliwia zalogowanie się użytkownikowi posiadającemu aktywne konto. | N-09 | poprawne dane otwierają sesję; błędne dane nie otwierają sesji |
| FR-02 | System ogranicza dostępne czynności na podstawie roli zalogowanego użytkownika. | N-09 | testy uprawnień dla trzech ról |
| FR-03 | System umożliwia studentowi wyświetlenie przyszłych terminów, które nie zostały anulowane i mają wolne miejsca. | N-01, N-04 | lista nie zawiera terminu przeszłego, anulowanego ani pełnego |
| FR-04 | System umożliwia studentowi filtrowanie listy konsultacji według wykładowcy. | N-02 | wyniki odpowiadają wybranemu wykładowcy |
| FR-05 | System umożliwia studentowi filtrowanie konsultacji według daty lub zakresu dat. | N-02 | w wynikach są wyłącznie terminy w wybranym zakresie |
| FR-06 | System umożliwia wyświetlenie szczegółów wybranego terminu konsultacji. | N-03 | szczegóły obejmują co najmniej wykładowcę, datę, czas, status i liczbę wolnych miejsc; miejsce/forma po potwierdzeniu |
| FR-07 | System umożliwia studentowi zapisanie się na dostępny termin konsultacji. | N-04 | po udanym zapisie powstaje aktywny zapis |
| FR-08 | System sprawdza aktualną dostępność miejsca w chwili zatwierdzania zapisu. | N-04 | dwie równoczesne próby ostatniego miejsca nie mogą obie zostać zaakceptowane |
| FR-09 | System nie tworzy drugiego aktywnego zapisu tego samego studenta na ten sam termin. | N-04 | ponowna próba jest odrzucona bez utworzenia duplikatu |
| FR-10 | System umożliwia studentowi anulowanie własnego aktywnego zapisu. | N-05 | status zapisu zmienia się na Anulowany, miejsce staje się dostępne zgodnie z limitem |
| FR-11 | System umożliwia wykładowcy utworzenie nowego terminu konsultacji. | N-06 | zapis poprawnych danych tworzy termin widoczny na liście |
| FR-12 | System umożliwia wykładowcy edycję terminu, jeśli nie ma on aktywnych zapisów. | N-06 | próba edycji obsadzonego terminu jest zablokowana w v1 |
| FR-13 | System umożliwia wykładowcy wyświetlenie listy zapisanych studentów dla własnego terminu. | N-07, N-09 | wykładowca nie widzi list zapisów innych wykładowców |
| FR-14 | System umożliwia wykładowcy anulowanie własnego terminu konsultacji. | N-06 | termin znika z listy dostępnych; powiązane zapisy zachowują czytelny status anulowania |
| FR-15 | System umożliwia administratorowi aktywowanie i dezaktywowanie kont oraz przypisywanie ról. | N-08 | zmiana roli wpływa na uprawnienia przy następnym żądaniu / logowaniu zgodnie z projektem |
| FR-16 | System wyświetla status zapisu użytkownikowi, którego ten zapis dotyczy. | N-10 | status jest czytelny po zapisie, anulowaniu i odwołaniu konsultacji |
| FR-17 | System wyświetla komunikat o powodzeniu lub przyczynie odrzucenia operacji zapisu. | N-10 | komunikat nie może potwierdzać zapisu, który nie został faktycznie utworzony |
| FR-18 | System odrzuca próbę zapisu na termin przeszły, anulowany lub pozbawiony wolnych miejsc. | N-04, N-10 | trzy scenariusze negatywne; część kontroli jest wspólna z FR-03 i FR-08 |

## 3. Wymagania niefunkcjonalne (NFR)

Wartości poniżej są wstępnymi, mierzalnymi kryteriami jakości, zaproponowanymi przez zespół. Należy je zweryfikować z klientem i dostosować do uzgodnionej skali systemu.

| ID | Obszar jakości (wstępny) | Treść (mierzalna) | Źródło | Sposób weryfikacji |
| --- | --- | --- | --- | --- |
| NFR-01 | Przydatność funkcjonalna | Przed odbiorem każde uzgodnione wymaganie funkcjonalne musi mieć co najmniej jeden opisany i wykonany test akceptacyjny. | N-01, N-04, N-05, N-06, N-09, N-10 | lista kontrolna testów powiązana z identyfikatorami FR |
| NFR-02 | Wydajność | Przy bazie testowej zawierającej 5 000 terminów i 50 równoczesnych użytkownikach 95% wyszukiwań ma zwrócić wyniki w czasie poniżej 2 sekund. | N-01, N-02 | test obciążeniowy po implementacji; zapisać konfigurację i wynik |
| NFR-03 | Kompatybilność | Kluczowe przepływy przeglądania i zapisu mają działać w dwóch najnowszych stabilnych wersjach Chrome, Firefox i Edge dostępnych w dniu testu. | N-01, N-04 | macierz testów przeglądarek |
| NFR-04 | Zdolność interakcji / użyteczność | Co najmniej 4 z 5 osób testujących, które wcześniej nie korzystały z systemu, mają ukończyć zapis na konsultację w mniej niż 3 minuty bez pomocy prowadzącego test. | N-04, N-10 | krótki test użyteczności; zapisać zadanie i czas |
| NFR-05 | Niezawodność | W 100 powtórzeniach scenariusza równoczesnej rezerwacji ostatniego miejsca system nie może potwierdzić więcej zapisów niż wynosi limit. | N-04 | test współbieżności na danych testowych |
| NFR-06 | Bezpieczeństwo | 100% przygotowanych przypadków kontroli dostępu dla ról student, wykładowca i administrator musi zakończyć się zgodnie z macierzą uprawnień; brak uprawnień nie może zmieniać danych. | N-09 | testy negatywne dla wszystkich operacji chronionych; przegląd uprawnień |
| NFR-07 | Utrzymywalność | Każda potwierdzona reguła dotycząca zapisu, anulowania lub zarządzania terminem musi mieć co najmniej jeden opisany test akceptacyjny przed zakończeniem implementacji. | N-04, N-05, N-06 | przegląd mapowania reguł na testy |
| NFR-08 | Elastyczność / przenośność | Podstawowe ekrany muszą pozostać czytelne i nie wymagać poziomego przewijania przy szerokości widoku 360 px, 768 px i 1366 px. | N-01, N-04 | kontrola w trzech szerokościach widoku |

## 4. Materiały do dalszej weryfikacji

- [Pytania do klienta](spotkania/pytania-do-klienta.md) — pytania dotyczące procesu, ról, reguł, danych i priorytetów.
- [Protokół wywiadu](spotkania/wywiad-1.md) — uzupełnić rzeczywistymi ustaleniami, cytatami i terminami.
- [Otwarte kwestie](12-otwarte-kwestie.md) — pytania, które wymagają odpowiedzi lub jawnej decyzji zespołu.

Potrzeby, wymagania i kryteria jakości oparte wyłącznie na założeniach zespołu pozostają wstępne do czasu ich weryfikacji.

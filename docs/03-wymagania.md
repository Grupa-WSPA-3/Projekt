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

Wartości poniżej są kryteriami projektowymi dla prototypu / przyszłej implementacji. Jeśli po konsultacji z prowadzącym lub klientem skala systemu okaże się inna, zmiana musi zostać odnotowana wraz z uzasadnieniem. Kategorie odnoszą się do modelu jakości produktu ISO/IEC 25010; norma opisuje charakterystyki jakości produktu. Oficjalna karta normy: https://www.iso.org/standard/78176.html.

| ID | Kategoria (ISO/IEC 25010) | Treść (mierzalna) | Źródło | Sposób weryfikacji |
| --- | --- | --- | --- | --- |
| NFR-01 | Przydatność funkcjonalna | Przed odbiorem każde uzgodnione wymaganie funkcjonalne musi mieć co najmniej jeden opisany i wykonany test akceptacyjny. | N-01, N-04, N-05, N-06, N-09, N-10 | lista kontrolna testów powiązana z identyfikatorami FR |
| NFR-02 | Wydajność | Przy bazie testowej zawierającej 5 000 terminów i 50 równoczesnych użytkownikach 95% wyszukiwań ma zwrócić wyniki w czasie poniżej 2 sekund. | N-01, N-02 | test obciążeniowy po implementacji; zapisać konfigurację i wynik |
| NFR-03 | Kompatybilność | Kluczowe przepływy przeglądania i zapisu mają działać w dwóch najnowszych stabilnych wersjach Chrome, Firefox i Edge dostępnych w dniu testu. | N-01, N-04 | macierz testów przeglądarek |
| NFR-04 | Zdolność interakcji / użyteczność | Co najmniej 4 z 5 osób testujących, które wcześniej nie korzystały z systemu, mają ukończyć zapis na konsultację w mniej niż 3 minuty bez pomocy prowadzącego test. | N-04, N-10 | krótki test użyteczności; zapisać zadanie i czas |
| NFR-05 | Niezawodność | W 100 powtórzeniach scenariusza równoczesnej rezerwacji ostatniego miejsca system nie może potwierdzić więcej zapisów niż wynosi limit. | N-04 | test współbieżności na danych testowych |
| NFR-06 | Bezpieczeństwo | 100% przygotowanych przypadków kontroli dostępu dla ról student, wykładowca i administrator musi zakończyć się zgodnie z macierzą uprawnień; brak uprawnień nie może zmieniać danych. | N-09 | testy negatywne dla wszystkich operacji chronionych; przegląd uprawnień |
| NFR-07 | Utrzymywalność | Każda potwierdzona reguła dotycząca zapisu, anulowania lub zarządzania terminem musi mieć co najmniej jeden opisany test akceptacyjny przed zakończeniem implementacji. | N-04, N-05, N-06 | przegląd mapowania reguł na testy |
| NFR-08 | Elastyczność / przenośność | Podstawowe ekrany muszą pozostać czytelne i nie wymagać poziomego przewijania przy szerokości widoku 360 px, 768 px i 1366 px. | N-01, N-04 | kontrola w trzech szerokościach widoku |

**Charakterystyka Safety (bezpieczeństwo w rozumieniu zagrożeń dla ludzi/otoczenia):** obecnie uznajemy ją za nieadekwatną do systemu rejestracji konsultacji, ponieważ system nie steruje urządzeniami ani procesami fizycznymi. Ryzyka organizacyjne i integralność zapisów pokrywają NFR-05 i NFR-06. Założenie należy ponownie ocenić, jeżeli zakres systemu się zmieni.

## 4. Wstępne reguły biznesowe (BR) — hipotezy do potwierdzenia

| ID | Reguła | Źródło | Dotyczy |
|---|---|---|---|
| BR-01 | Początek terminu musi być wcześniejszy niż jego koniec, a nowy termin nie może rozpoczynać się w przeszłości. | N-06; założenie do potwierdzenia | FR-11, FR-12 |
| BR-02 | Liczba aktywnych zapisów dla terminu nie może przekroczyć ustawionego limitu miejsc. Domyślny limit wynosi 1, dopóki nie zostanie potwierdzona obsługa konsultacji grupowych. | N-04; założenie do potwierdzenia | FR-03, FR-07, FR-08, FR-18 |
| BR-03 | Student może mieć tylko jeden aktywny zapis na dany termin. | N-04; założenie do potwierdzenia | FR-09 |
| BR-04 | Student może anulować wyłącznie własny zapis; wykładowca może zarządzać i anulować wyłącznie własne terminy; administrator zarządza kontami i rolami. | N-05, N-06, N-08, N-09 | FR-02, FR-10, FR-12, FR-13, FR-14, FR-15 |
| BR-05 | Termin z co najmniej jednym aktywnym zapisem nie może być edytowany w zakresie daty i godziny w wersji podstawowej. Wykładowca powinien anulować termin i utworzyć nowy. | N-06; założenie do potwierdzenia | FR-12, FR-14 |
| BR-06 | Anulowany termin nie jest dostępny dla nowych zapisów, a powiązane zapisy pozostają możliwe do rozpoznania jako anulowane. | N-06, N-10; założenie do potwierdzenia | FR-14, FR-16, FR-18 |
| BR-07 | Aktywny zapis zajmuje jedno miejsce; anulowany zapis nie zajmuje miejsca. | N-04, N-05; założenie do potwierdzenia | FR-08, FR-10 |
| BR-08 | Lista zapisów zawierająca dane studentów jest widoczna wyłącznie dla wykładowcy danego terminu oraz uprawnionego administratora, jeśli taki dostęp zostanie uzasadniony. | N-07, N-09 | FR-02, FR-13 |
| BR-09 | Każde konto ma jedną podstawową rolę: Student, Wykładowca albo Administrator. Obsługa wielu ról jednego konta nie należy do pierwszej wersji. | N-08, N-09; założenie do potwierdzenia | FR-02, FR-15 |

## 5. Ograniczenia i założenia

1. Pierwsza wersja nie prowadzi wideokonferencji ani rozmów audio.
2. Pierwsza wersja nie wysyła automatycznych powiadomień e-mail/SMS.
3. Pierwsza wersja nie synchronizuje dostępności z uczelnianym planem zajęć ani systemem SSO.
4. System nie obsługuje płatności, ocen, egzaminów ani pełnego harmonogramu dydaktycznego.
5. Natywna aplikacja mobilna pozostaje poza zakresem; responsywny widok webowy jest objęty NFR-08.
6. Wymagania i reguły oparte wyłącznie na hipotezach nie mogą zostać uznane za ostateczne bez weryfikacji przez zespół / klienta.
7. Technologia implementacji nie została zatwierdzona; jej wybór wymaga osobnej decyzji po modelowaniu procesu, danych i architektury.

## 6. Pytania otwarte

Pełna lista, właściciele i status znajdują się w `docs/12-otwarte-kwestie.md`. Najważniejsze kwestie do rozstrzygnięcia przed finalizacją wymagań:

1. Czy limit miejsc może być większy niż 1 i kto go ustala?
2. Czy student może anulować zapis do samego początku konsultacji?
3. Jak są tworzone konta i kto je aktywuje?
4. Czy terminy mogą być cykliczne?
5. Jakie informacje o konsultacji muszą być widoczne na liście?
6. Czy administrator może zobaczyć listę zapisanych studentów?
7. Czy potrzebny jest link do spotkania online, mimo że wideokonferencja jest poza zakresem?
8. Czy czas systemowy zawsze odpowiada `Europe/Warsaw`?

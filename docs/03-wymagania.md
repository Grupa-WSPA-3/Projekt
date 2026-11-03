# Wymagania — System obsługi konsultacji wykładowców (SKW)

**Wersja:** 0.2 — robocza, zgodna ze strukturą z zajęć 4  
**Autorzy:** zespół SKW  
**Status:** do przeglądu zespołu i weryfikacji na podstawie wywiadu z klientem.

> **Źródła i uczciwość analizy:** w przekazanym archiwum nie znaleziono notatki z przeprowadzonego wywiadu. Identyfikatory N-xx poniżej wyprowadzono z karty projektu zespołu i oznaczono jako hipotezy do potwierdzenia. Po rzeczywistym wywiadzie należy poprawić źródła i treść, zachowując istniejące identyfikatory.

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

| ID | Treść | Źródło | Priorytet | Uwagi |
|---|---|---|---|---|
| FR-01 | System umożliwia zalogowanie się użytkownikowi posiadającemu aktywne konto. | N-09 | Must | poprawne dane otwierają sesję; błędne dane nie otwierają sesji |
| FR-02 | System ogranicza dostępne czynności na podstawie roli zalogowanego użytkownika. | N-09 | Must | testy uprawnień dla trzech ról |
| FR-03 | System umożliwia studentowi wyświetlenie przyszłych terminów, które nie zostały anulowane i mają wolne miejsca. | N-01, N-04 | Must | lista nie zawiera terminu przeszłego, anulowanego ani pełnego |
| FR-04 | System umożliwia studentowi filtrowanie listy konsultacji według wykładowcy. | N-02 | Should | wyniki odpowiadają wybranemu wykładowcy |
| FR-05 | System umożliwia studentowi filtrowanie konsultacji według daty lub zakresu dat. | N-02 | Should | w wynikach są wyłącznie terminy w wybranym zakresie |
| FR-06 | System umożliwia wyświetlenie szczegółów wybranego terminu konsultacji. | N-03 | Should | szczegóły obejmują co najmniej wykładowcę, datę, czas, status i liczbę wolnych miejsc; miejsce/forma po potwierdzeniu |
| FR-07 | System umożliwia studentowi zapisanie się na dostępny termin konsultacji. | N-04 | Must | po udanym zapisie powstaje aktywny zapis |
| FR-08 | System sprawdza aktualną dostępność miejsca w chwili zatwierdzania zapisu. | N-04 | Must | dwie równoczesne próby ostatniego miejsca nie mogą obie zostać zaakceptowane |
| FR-09 | System nie tworzy drugiego aktywnego zapisu tego samego studenta na ten sam termin. | N-04 | Must | ponowna próba jest odrzucona bez utworzenia duplikatu |
| FR-10 | System umożliwia studentowi anulowanie własnego aktywnego zapisu. | N-05 | Must | status zapisu zmienia się na Anulowany, miejsce staje się dostępne zgodnie z limitem |
| FR-11 | System umożliwia wykładowcy utworzenie nowego terminu konsultacji. | N-06 | Must | zapis poprawnych danych tworzy termin widoczny na liście |
| FR-12 | System umożliwia wykładowcy edycję terminu, jeśli nie ma on aktywnych zapisów. | N-06 | Should | próba edycji obsadzonego terminu jest zablokowana w v1 |
| FR-13 | System umożliwia wykładowcy wyświetlenie listy zapisanych studentów dla własnego terminu. | N-07, N-09 | Should | wykładowca nie widzi list zapisów innych wykładowców |
| FR-14 | System umożliwia wykładowcy anulowanie własnego terminu konsultacji. | N-06 | Must | termin znika z listy dostępnych; powiązane zapisy zachowują czytelny status anulowania |
| FR-15 | System umożliwia administratorowi aktywowanie i dezaktywowanie kont oraz przypisywanie ról. | N-08 | Should | zmiana roli wpływa na uprawnienia przy następnym żądaniu / logowaniu zgodnie z projektem |
| FR-16 | System wyświetla status zapisu użytkownikowi, którego ten zapis dotyczy. | N-10 | Should | status jest czytelny po zapisie, anulowaniu i odwołaniu konsultacji |
| FR-17 | System wyświetla komunikat o powodzeniu lub przyczynie odrzucenia operacji zapisu. | N-10 | Must | komunikat nie może potwierdzać zapisu, który nie został faktycznie utworzony |
| FR-18 | System odrzuca próbę zapisu na termin przeszły, anulowany lub pozbawiony wolnych miejsc. | N-04, N-10 | Should | trzy scenariusze negatywne; część kontroli jest wspólna z FR-03 i FR-08 |

## 3. Wymagania niefunkcjonalne (NFR)

Wartości poniżej są kryteriami projektowymi dla prototypu / przyszłej implementacji. Jeśli po konsultacji z prowadzącym lub klientem skala systemu okaże się inna, zmiana musi zostać odnotowana wraz z uzasadnieniem. Kategorie odnoszą się do modelu jakości produktu ISO/IEC 25010; norma opisuje charakterystyki jakości produktu. Oficjalna karta normy: https://www.iso.org/standard/78176.html.

| ID | Kategoria (ISO/IEC 25010) | Treść (mierzalna) | Źródło | Priorytet | Uwagi (sposób sprawdzenia) |
|---|---|---|---|---|---|
| NFR-01 | Przydatność funkcjonalna | Przed wydaniem 100% historyjek Must musi przejść wszystkie zapisane kryteria Given/When/Then. | N-01, N-04, N-05, N-06, N-09, N-10 | Must | lista akceptacyjna powiązana z US i testami |
| NFR-02 | Wydajność | Przy bazie testowej zawierającej 5 000 terminów i 50 równoczesnych użytkownikach 95% wyszukiwań ma zwrócić wyniki w czasie poniżej 2 sekund. | N-01, N-02 | Should | test obciążeniowy po implementacji; zapisać konfigurację i wynik |
| NFR-03 | Kompatybilność | Kluczowe przepływy przeglądania i zapisu mają działać w dwóch najnowszych stabilnych wersjach Chrome, Firefox i Edge dostępnych w dniu testu. | N-01, N-04 | Should | macierz testów przeglądarek |
| NFR-04 | Zdolność interakcji / użyteczność | Co najmniej 4 z 5 osób testujących, które wcześniej nie korzystały z systemu, mają ukończyć zapis na konsultację w mniej niż 3 minuty bez pomocy prowadzącego test. | N-04, N-10 | Should | krótki test użyteczności; zapisać zadanie i czas |
| NFR-05 | Niezawodność | W 100 powtórzeniach scenariusza równoczesnej rezerwacji ostatniego miejsca system nie może potwierdzić więcej zapisów niż wynosi limit. | N-04 | Must | test współbieżności na danych testowych |
| NFR-06 | Bezpieczeństwo | 100% przygotowanych przypadków kontroli dostępu dla ról student, wykładowca i administrator musi zakończyć się zgodnie z macierzą uprawnień; brak uprawnień nie może zmieniać danych. | N-09 | Must | testy negatywne dla wszystkich operacji chronionych; przegląd uprawnień |
| NFR-07 | Utrzymywalność | Każda reguła BR związana z rezerwacją musi mieć co najmniej jeden test automatyczny lub jawnie opisany test akceptacyjny przed zakończeniem implementacji. | N-04, N-05, N-06 | Should | przegląd mapowania BR → test |
| NFR-08 | Elastyczność / przenośność | Podstawowe ekrany muszą pozostać czytelne i nie wymagać poziomego przewijania przy szerokości widoku 360 px, 768 px i 1366 px. | N-01, N-04 | Should | kontrola w trzech szerokościach widoku |

**Charakterystyka Safety (bezpieczeństwo w rozumieniu zagrożeń dla ludzi/otoczenia):** obecnie uznajemy ją za nieadekwatną do systemu rejestracji konsultacji, ponieważ system nie steruje urządzeniami ani procesami fizycznymi. Ryzyka organizacyjne i integralność zapisów pokrywają NFR-05 i NFR-06. Założenie należy ponownie ocenić, jeżeli zakres systemu się zmieni.

## 4. Reguły biznesowe (BR)

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

## 5. Ograniczenia

1. Pierwsza wersja nie prowadzi wideokonferencji ani rozmów audio.
2. Pierwsza wersja nie wysyła automatycznych powiadomień e-mail/SMS.
3. Pierwsza wersja nie synchronizuje dostępności z uczelnianym planem zajęć ani systemem SSO.
4. System nie obsługuje płatności, ocen, egzaminów ani pełnego harmonogramu dydaktycznego.
5. Natywna aplikacja mobilna pozostaje poza zakresem; responsywny widok webowy jest objęty NFR-08.
6. Wymagania i reguły oparte wyłącznie na hipotezach nie mogą zostać uznane za ostateczne bez weryfikacji przez zespół / klienta.
7. Technologia implementacji nie została zatwierdzona; jej wybór wymaga osobnej decyzji po modelowaniu procesu, danych i architektury.

## 6. Historyjki użytkownika i kryteria akceptacji

### US-01: Logowanie i dostęp zgodny z rolą

**Jako** użytkownik z aktywnym kontem **chcę** zalogować się i korzystać z funkcji swojej roli, **aby** moje dane i działania były oddzielone od działań innych osób.  
**Wymagania:** FR-01, FR-02 · **Priorytet:** Must

**Scenariusz 1 — poprawne logowanie**
- **Given** użytkownik ma aktywne konto i poprawne dane logowania
- **When** wysyła formularz logowania
- **Then** system otwiera sesję tego użytkownika i udostępnia funkcje zgodne z jego rolą

**Scenariusz 2 — brak uprawnienia**
- **Given** student jest zalogowany
- **When** próbuje otworzyć operację dostępną wyłącznie wykładowcy
- **Then** system odmawia wykonania operacji i nie zmienia danych

### US-02: Przeglądanie dostępnych konsultacji

**Jako** student **chcę** zobaczyć przyszłe terminy z wolnymi miejscami, **aby** wybrać odpowiednią konsultację bez pisania do wykładowcy.  
**Wymagania:** FR-03 · **Priorytet:** Must

**Scenariusz 1 — lista dostępnych terminów**
- **Given** w systemie istnieją aktywne przyszłe terminy, w tym co najmniej jeden z wolnym miejscem
- **When** student otwiera listę konsultacji
- **Then** widzi tylko terminy, które nie są przeszłe, anulowane ani pełne

**Scenariusz 2 — brak dostępnych terminów**
- **Given** nie ma aktywnych przyszłych terminów z wolnymi miejscami
- **When** student otwiera listę
- **Then** system informuje o braku wyników i nie pokazuje fikcyjnych możliwości zapisu

### US-03: Zapis na konsultację

**Jako** student **chcę** zarezerwować wolne miejsce, **aby** mieć potwierdzony termin rozmowy z wykładowcą.  
**Wymagania:** FR-07, FR-08, FR-09, FR-17 · **Priorytet:** Must

**Scenariusz 1 — zapis udany**
- **Given** termin jest aktywny i ma co najmniej jedno wolne miejsce, a student nie ma na nim aktywnego zapisu
- **When** student zatwierdza zapis
- **Then** system tworzy jeden aktywny zapis i wyświetla potwierdzenie

**Scenariusz 2 — brak miejsca**
- **Given** limit terminu został osiągnięty
- **When** student próbuje zapisać się na ten termin
- **Then** system nie tworzy zapisu i wyświetla komunikat o braku miejsc

**Scenariusz 3 — dwie równoczesne próby ostatniego miejsca**
- **Given** pozostało dokładnie jedno wolne miejsce
- **When** dwóch różnych studentów zatwierdza zapis w tym samym czasie
- **Then** tylko jeden zapis zostaje aktywny, a drugi student dostaje informację o braku miejsca

**Scenariusz 4 — duplikat**
- **Given** student ma już aktywny zapis na wybrany termin
- **When** ponownie próbuje zapisać się na ten sam termin
- **Then** system nie tworzy drugiego aktywnego zapisu

### US-04: Anulowanie własnego zapisu

**Jako** student **chcę** anulować własny zapis, **aby** zwolnić miejsce, gdy nie mogę przyjść.  
**Wymagania:** FR-10 · **Priorytet:** Must

**Scenariusz 1 — anulowanie własnego zapisu**
- **Given** student ma aktywny zapis na termin
- **When** wybiera anulowanie i potwierdza operację
- **Then** status zapisu zmienia się na Anulowany, a miejsce przestaje być zajęte przez ten zapis

**Scenariusz 2 — próba anulowania zapisu innej osoby**
- **Given** student nie jest właścicielem zapisu
- **When** próbuje go anulować
- **Then** system odmawia operacji i zachowuje dotychczasowy status

### US-05: Utworzenie terminu przez wykładowcę

**Jako** wykładowca **chcę** utworzyć termin konsultacji, **aby** studenci mogli się na niego zapisać.  
**Wymagania:** FR-11 · **Priorytet:** Must

**Scenariusz 1 — poprawny termin**
- **Given** wykładowca jest zalogowany i wprowadza poprawny przyszły termin z końcem późniejszym niż początek
- **When** zapisuje termin
- **Then** termin zostaje zapisany i może być wyświetlony studentom zgodnie z jego dostępnością

**Scenariusz 2 — niepoprawny termin**
- **Given** data rozpoczęcia jest w przeszłości albo koniec nie następuje po początku
- **When** wykładowca próbuje zapisać termin
- **Then** system odrzuca dane i wskazuje przyczynę

### US-06: Anulowanie własnej konsultacji

**Jako** wykładowca **chcę** anulować termin, który nie może się odbyć, **aby** studenci nie zapisywali się na nieaktualną konsultację.  
**Wymagania:** FR-14 · **Priorytet:** Must

**Scenariusz 1 — poprawne anulowanie**
- **Given** termin należy do zalogowanego wykładowcy i jest aktywny
- **When** wykładowca potwierdza anulowanie
- **Then** termin przestaje być dostępny dla nowych zapisów, a powiązane zapisy mają czytelny status anulowania

**Scenariusz 2 — cudzy termin**
- **Given** termin należy do innego wykładowcy
- **When** wykładowca próbuje go anulować
- **Then** system odmawia operacji i nie zmienia terminu

## 7. Pytania otwarte

Pełna lista, właściciele i status znajdują się w `docs/12-otwarte-kwestie.md`. Najważniejsze kwestie do rozstrzygnięcia przed finalizacją wymagań:

1. Czy limit miejsc może być większy niż 1 i kto go ustala?
2. Czy student może anulować zapis do samego początku konsultacji?
3. Jak są tworzone konta i kto je aktywuje?
4. Czy terminy mogą być cykliczne?
5. Jakie informacje o konsultacji muszą być widoczne na liście?
6. Czy administrator może zobaczyć listę zapisanych studentów?
7. Czy potrzebny jest link do spotkania online, mimo że wideokonferencja jest poza zakresem?
8. Czy czas systemowy zawsze odpowiada `Europe/Warsaw`?

## 8. Priorytety MoSCoW — podsumowanie

| Priorytet | FR | Liczba | Udział |
|---|---|---:|---:|
| Must | FR-01, FR-02, FR-03, FR-07, FR-08, FR-09, FR-10, FR-11, FR-14, FR-17 | 10 | 55,6% |
| Should | FR-04, FR-05, FR-06, FR-12, FR-13, FR-15, FR-16, FR-18 | 8 | 44,4% |
| Could | brak w tej wersji tabeli FR | 0 | 0% |
| Won't now | funkcje wymienione w sekcji „Ograniczenia” | poza listą FR | — |

Priorytety są propozycją zespołu. Należy je zatwierdzić po wywiadzie; ważność nie wynika wyłącznie z trudności implementacji.

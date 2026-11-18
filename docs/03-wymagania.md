# Wymagania — System obsługi konsultacji wykładowców (SKW)

**Wersja:** 0.2 — specyfikacja robocza po analizie procesów  
**Status:** kompletna strukturalnie do przeglądu; wymagania oznaczone jako hipotezy nadal wymagają walidacji z klientem.  
**Zakres:** pierwsza wersja webowego systemu obsługi konsultacji.

> **Źródła i wiarygodność:** potrzeby N-xx wynikają z karty projektu i analizy zespołu. W przekazanych plikach nie znaleziono rzeczywistych odpowiedzi z wywiadu. Nie przedstawiamy zatem hipotez jako potwierdzonych wypowiedzi klienta. Aktualizacje FR/BR po walkthrough procesów są oznaczone w sekcji 9 i powinny zostać zatwierdzone przez zespół.

## 1. Potrzeby

| ID | Potrzeba / oczekiwanie | Kto | Źródło | Typ / status |
|---|---|---|---|---|
| N-01 | Student chce znaleźć aktualne przyszłe terminy konsultacji w jednym miejscu. | Student | Karta projektu 0.3, problem i zakres IN | potrzeba — hipoteza |
| N-02 | Student chce wyszukać konsultacje według wykładowcy i terminu. | Student | Karta projektu 0.3, funkcje | potrzeba — hipoteza |
| N-03 | Student potrzebuje informacji wystarczających do wyboru konsultacji. | Student | Karta projektu 0.3, dane terminu | potrzeba — pola do potwierdzenia |
| N-04 | Student chce zapisać się na dostępne miejsce bez ryzyka przekroczenia limitu. | Student / wykładowca | Karta projektu 0.3, problem i zakres IN | potrzeba — hipoteza |
| N-05 | Student chce anulować własny zapis bez kontaktu z wykładowcą. | Student | Karta projektu 0.3, zakres IN | potrzeba — hipoteza |
| N-06 | Wykładowca chce sam tworzyć, edytować i odwoływać własne terminy. | Wykładowca | Karta projektu 0.3, zakres IN | potrzeba — hipoteza |
| N-07 | Wykładowca chce sprawdzić listę studentów zapisanych na jego konsultację. | Wykładowca | Karta projektu 0.3, zakres IN | potrzeba — hipoteza |
| N-08 | Administrator potrzebuje możliwości zarządzania kontami i rolami. | Administrator | Karta projektu 0.3, role | potrzeba — hipoteza |
| N-09 | Użytkownik potrzebuje dostępu do czynności i danych odpowiednich dla swojej roli. | Student / wykładowca / administrator | Karta projektu 0.3, role i założenia | potrzeba projektowa |
| N-10 | Użytkownik potrzebuje jasnej informacji o wyniku zapisu, anulowania lub odwołania terminu. | Student / wykładowca | wniosek zespołu z analizy procesów | hipoteza projektowa |

## 2. Wymagania funkcjonalne (FR)

Priorytety dotyczą pierwszej wersji. Kryteria w tabeli są podstawą przyszłych testów akceptacyjnych.

| ID | Wymaganie | Źródło | Priorytet | Kryterium / sposób sprawdzenia |
|---|---|---|---|---|
| FR-01 | System umożliwia zalogowanie się użytkownikowi posiadającemu aktywne konto. | N-09 | Must | poprawne dane otwierają sesję; błędne nie otwierają |
| FR-02 | System ogranicza dostępne czynności na podstawie roli zalogowanego użytkownika. | N-09 | Must | student, wykładowca i administrator mają odrębne uprawnienia |
| FR-03 | System umożliwia studentowi wyświetlenie przyszłych, aktywnych terminów, które mają wolne miejsca. | N-01, N-04 | Must | brak terminów przeszłych, anulowanych i pełnych na liście dostępnych |
| FR-04 | System umożliwia filtrowanie konsultacji według wykładowcy. | N-02 | Should | wyniki odpowiadają wybranemu wykładowcy |
| FR-05 | System umożliwia filtrowanie konsultacji według daty lub zakresu dat. | N-02 | Should | wyniki mieszczą się w wybranym zakresie |
| FR-06 | System umożliwia wyświetlenie szczegółów terminu przed zapisem. | N-03 | Should | szczegóły zawierają co najmniej wykładowcę, datę, godzinę, status i liczbę wolnych miejsc; miejsce / forma po potwierdzeniu |
| FR-07 | System umożliwia studentowi zapisanie się na dostępny termin konsultacji. | N-04 | Must | po udanym zapisie powstaje jeden aktywny zapis |
| FR-08 | System sprawdza dostępność miejsca atomowo w chwili zatwierdzania zapisu, a nie tylko podczas wcześniejszego wyświetlania listy. | N-04 | Must | przy dwóch równoczesnych próbach ostatniego miejsca tylko jedna kończy się sukcesem |
| FR-09 | System nie tworzy drugiego aktywnego zapisu tego samego studenta na ten sam termin. | N-04 | Must | ponowna próba jest odrzucona bez duplikatu |
| FR-10 | System umożliwia studentowi anulowanie własnego aktywnego zapisu. | N-05 | Must | status zmienia się na Anulowany, a miejsce przestaje być zajęte przez ten zapis |
| FR-11 | System umożliwia wykładowcy utworzenie nowego terminu konsultacji. | N-06 | Must | poprawny przyszły termin zostaje zapisany i może być wyświetlony studentom |
| FR-12 | System umożliwia wykładowcy edycję własnego terminu, jeżeli nie ma on aktywnych zapisów. | N-06 | Should | edycja terminu z aktywnymi zapisami jest blokowana w v1 |
| FR-13 | System umożliwia wykładowcy wyświetlenie listy zapisanych studentów dla własnego terminu. | N-07, N-09 | Should | wykładowca nie widzi list zapisów innych wykładowców |
| FR-14 | System umożliwia wykładowcy anulowanie własnego terminu i oznacza powiązane aktywne zapisy jako dotknięte odwołaniem terminu. | N-06, N-10 | Must | termin znika z listy dostępnych; status terminu i powiązanych zapisów jest jednoznaczny |
| FR-15 | System umożliwia administratorowi aktywowanie i dezaktywowanie kont oraz przypisywanie ról. | N-08 | Should | zmiana roli wpływa na uprawnienia zgodnie z przyjętą sesją |
| FR-16 | System wyświetla użytkownikowi status dotyczący jego zapisu lub odwołanego terminu. | N-10 | Should | status jest widoczny na liście własnych zapisów |
| FR-17 | System wyświetla komunikat o powodzeniu lub przyczynie odrzucenia operacji zapisu. | N-10 | Must | komunikat nie potwierdza operacji, która nie została zapisana |
| FR-18 | System odrzuca próbę zapisu na termin przeszły, anulowany lub pozbawiony wolnych miejsc. | N-04, N-10 | Should | oddzielne testy dla terminu przeszłego, anulowanego i pełnego |

## 3. Wymagania niefunkcjonalne (NFR)

Wartości są mierzalnymi kryteriami projektowymi dla prototypu / przyszłej implementacji. Profil obciążenia i progi należy zatwierdzić po poznaniu skali rzeczywistego wdrożenia.

| ID | Kategoria jakości | Wymaganie mierzalne | Źródło | Priorytet | Sposób weryfikacji |
|---|---|---|---|---|---|
| NFR-01 | Przydatność funkcjonalna (*functional suitability*) | Przed odbiorem 100% historyjek Must przechodzi wszystkie zapisane kryteria GWT. | N-01, N-04, N-05, N-06, N-09, N-10 | Must | lista akceptacyjna powiązana z US i testami |
| NFR-02 | Efektywność działania (*performance efficiency*) | Przy bazie testowej 5 000 terminów i 50 równoczesnych użytkownikach 95% wyszukiwań zwraca wyniki w czasie poniżej 2 sekund. | N-01, N-02 | Should | test obciążeniowy po implementacji |
| NFR-03 | Kompatybilność (*compatibility*) | Kluczowe przepływy działają w dwóch najnowszych stabilnych wersjach Chrome, Firefox i Edge dostępnych w dniu testu. | N-01, N-04 | Should | macierz testów przeglądarek |
| NFR-04 | Zdolność interakcji (*interaction capability*) | Co najmniej 4 z 5 nowych testerów kończy zapis w czasie poniżej 3 minut bez pomocy. | N-04, N-10 | Should | test użyteczności z pomiarem czasu |
| NFR-05 | Niezawodność (*reliability*) | W 100 powtórzeniach równoczesnego zapisu na ostatnie miejsce liczba aktywnych zapisów nie przekracza limitu. | N-04 | Must | test współbieżności |
| NFR-06 | Bezpieczeństwo (*security*) | 100% przypadków testowych kontroli uprawnień dla trzech ról kończy się zgodnie z macierzą; brak uprawnień nie zmienia danych. | N-09 | Must | testy negatywne i przegląd autoryzacji |
| NFR-07 | Utrzymywalność (*maintainability*) | Każda reguła BR dotycząca zapisu, anulowania i zarządzania terminem ma co najmniej jeden opisany test przed odbiorem. | N-04, N-05, N-06 | Should | przegląd mapowania BR → test |
| NFR-08 | Elastyczność (*flexibility*, adaptowalność) | Podstawowe widoki pozostają czytelne bez poziomego przewijania przy szerokości 360 px, 768 px i 1366 px. | N-01, N-04 | Should | kontrola responsywności w trzech szerokościach |

**Safety (bezpieczeństwo w rozumieniu ISO/IEC 25010:2023):** dziewiąta charakterystyka modelu została rozważona, ale uznana za nieadekwatną dla SKW w obecnym zakresie. System nie steruje urządzeniami ani procesami fizycznymi i nie stwarza zagrożeń dla ludzi lub otoczenia. Należy ponownie ocenić tę decyzję, jeśli zakres systemu się zmieni. Źródło: [ISO/IEC 25010:2023 — Product quality model](https://www.iso.org/standard/78176.html).

## 4. Reguły biznesowe (BR)

| ID | Reguła | Źródło / status | Powiązane FR |
|---|---|---|---|
| BR-01 | Początek terminu musi być wcześniejszy niż jego koniec, a nowy termin nie może rozpoczynać się w przeszłości. | N-06; założenie zespołu | FR-11, FR-12 |
| BR-02 | Liczba aktywnych zapisów dla terminu nie może przekroczyć limitu miejsc. Domyślny limit wynosi 1 do czasu potwierdzenia konsultacji grupowych. | N-04; do potwierdzenia | FR-03, FR-07, FR-08, FR-18 |
| BR-03 | Student może mieć tylko jeden aktywny zapis na dany termin. | N-04; do potwierdzenia | FR-09 |
| BR-04 | Student anuluje wyłącznie własny zapis; wykładowca zarządza wyłącznie własnymi terminami; administrator zarządza kontami i rolami. | N-05, N-06, N-08, N-09 | FR-02, FR-10, FR-12, FR-13, FR-14, FR-15 |
| BR-05 | W v1 termin z aktywnymi zapisami nie może być edytowany w zakresie daty i godziny; wykładowca anuluje go i tworzy nowy termin. | N-06; do potwierdzenia | FR-12, FR-14 |
| BR-06 | Anulowany termin nie jest dostępny dla nowych zapisów; powiązane zapisy muszą mieć jednoznaczny status odwołania terminu. | N-06, N-10 | FR-14, FR-16, FR-18 |
| BR-07 | Aktywny zapis zajmuje jedno miejsce; anulowany zapis nie zajmuje miejsca. | N-04, N-05 | FR-08, FR-10 |
| BR-08 | Lista zawierająca dane studentów jest widoczna wyłącznie dla wykładowcy danego terminu oraz administratora, jeżeli taki dostęp zostanie uzasadniony i zatwierdzony. | N-07, N-09; zakres admina otwarty | FR-02, FR-13 |
| BR-09 | Każde konto ma jedną podstawową rolę: Student, Wykładowca albo Administrator. | N-08, N-09; założenie do potwierdzenia | FR-02, FR-15 |
| BR-10 | Termin można zarezerwować tylko wtedy, gdy w chwili zatwierdzania jest aktywny, rozpoczyna się w przyszłości i ma co najmniej jedno wolne miejsce. Samo wcześniejsze wyświetlenie terminu nie rezerwuje miejsca. | walkthrough P-01; nowa reguła do zatwierdzenia | FR-03, FR-07, FR-08, FR-18 |

## 5. Ograniczenia

1. v1 nie prowadzi wideokonferencji ani rozmów audio.
2. v1 nie wysyła automatycznych powiadomień e-mail/SMS; komunikaty w aplikacji są częścią zakresu.
3. v1 nie synchronizuje danych z uczelnianym planem zajęć ani zewnętrznym SSO.
4. System nie obsługuje płatności, ocen, egzaminów ani pełnego planu dydaktycznego.
5. Natywna aplikacja mobilna pozostaje poza zakresem; widok webowy ma być responsywny.
6. Technologia implementacji nie została zatwierdzona; wybór wymaga osobnej decyzji.
7. Reguły oznaczone jako założenia nie stają się potwierdzonymi wymaganiami bez walidacji.

## 6. Historyjki użytkownika i kryteria akceptacji

### US-01 — Logowanie i dostęp zgodny z rolą
**Jako** użytkownik z aktywnym kontem **chcę** zalogować się i korzystać z funkcji swojej roli, **aby** moje działania i dane były chronione.  
**Wymagania:** FR-01, FR-02 · **Priorytet:** Must

- **Given** użytkownik ma aktywne konto i poprawne dane, **When** wysyła formularz logowania, **Then** system otwiera sesję i udostępnia funkcje zgodne z rolą.
- **Given** student jest zalogowany, **When** próbuje wykonać operację wykładowcy, **Then** system odmawia i nie zmienia danych.

### US-02 — Przeglądanie i wyszukiwanie konsultacji
**Jako** student **chcę** zobaczyć przyszłe terminy z wolnymi miejscami i zawęzić listę, **aby** wybrać odpowiednią konsultację.  
**Wymagania:** FR-03, FR-04, FR-05, FR-06 · **Priorytet:** Must (FR-03), Should (FR-04…06)

- **Given** istnieją przyszłe aktywne terminy, **When** student otwiera listę, **Then** system pokazuje wyłącznie terminy dostępne do zapisu.
- **Given** student wybiera wykładowcę i zakres dat, **When** stosuje filtry, **Then** system pokazuje wyniki zgodne z oboma kryteriami.
- **Given** student otwiera szczegóły terminu, **When** wyświetla się karta konsultacji, **Then** widzi dane konieczne do podjęcia decyzji i liczbę wolnych miejsc.

### US-03 — Zapis na konsultację
**Jako** student **chcę** zarezerwować wolne miejsce, **aby** mieć potwierdzony termin rozmowy z wykładowcą.  
**Wymagania:** FR-07, FR-08, FR-09, FR-17, FR-18 · **Priorytet:** Must (FR-07/08/09/17), Should (FR-18)

- **Given** termin jest aktywny, przyszły, ma wolne miejsce, a student nie ma na nim aktywnego zapisu, **When** zatwierdza zapis, **Then** system tworzy dokładnie jeden aktywny zapis i pokazuje potwierdzenie.
- **Given** pozostało jedno miejsce, **When** dwóch studentów próbuje zapisać się równocześnie, **Then** aktywny jest najwyżej jeden nowy zapis.
- **Given** student ma już aktywny zapis na termin, **When** ponawia próbę, **Then** system nie tworzy duplikatu.
- **Given** termin jest przeszły, anulowany lub pełny, **When** student próbuje się zapisać, **Then** system odrzuca operację i podaje przyczynę.

### US-04 — Anulowanie własnego zapisu
**Jako** student **chcę** anulować własny zapis, **aby** zwolnić miejsce, gdy nie mogę przyjść.  
**Wymagania:** FR-10, FR-16 · **Priorytet:** Must (FR-10), Should (FR-16)

- **Given** student ma aktywny własny zapis, **When** potwierdza anulowanie, **Then** status zmienia się na Anulowany, a miejsce przestaje być zajęte.
- **Given** zapis należy do innej osoby albo jest już anulowany, **When** student próbuje go anulować, **Then** system odmawia bez zmiany danych.

### US-05 — Zarządzanie terminami przez wykładowcę
**Jako** wykładowca **chcę** tworzyć, edytować i anulować własne terminy, **aby** utrzymywać aktualną ofertę konsultacji.  
**Wymagania:** FR-11, FR-12, FR-14, FR-16 · **Priorytet:** Must (FR-11/14), Should (FR-12/16)

- **Given** wykładowca wprowadza przyszły termin z poprawnym zakresem czasu, **When** zapisuje termin, **Then** termin zostaje utworzony.
- **Given** termin ma aktywne zapisy, **When** wykładowca próbuje zmienić datę lub godzinę, **Then** system blokuje edycję zgodnie z BR-05.
- **Given** termin należy do wykładowcy, **When** wykładowca potwierdza jego anulowanie, **Then** termin przestaje być dostępny, a jego zapisani studenci widzą właściwy status.

### US-06 — Lista zapisów dla wykładowcy
**Jako** wykładowca **chcę** zobaczyć listę studentów zapisanych na mój termin, **aby** przygotować się do konsultacji.  
**Wymagania:** FR-13 · **Priorytet:** Should

- **Given** wykładowca jest właścicielem terminu, **When** otwiera listę zapisów, **Then** widzi zapisy wyłącznie do własnej konsultacji.
- **Given** wykładowca próbuje otworzyć listę innego wykładowcy, **When** system sprawdza właściciela terminu, **Then** odmawia dostępu i nie ujawnia danych studentów.

### US-07 — Zarządzanie kontami i rolami przez administratora
**Jako** administrator **chcę** aktywować i dezaktywować konta oraz przypisywać role, **aby** dostęp do systemu miały wyłącznie uprawnione osoby.  
**Wymagania:** FR-15 · **Priorytet:** Should

- **Given** administrator jest zalogowany, **When** dezaktywuje konto użytkownika, **Then** konto traci możliwość rozpoczęcia nowej sesji.
- **Given** użytkownik nie ma roli administratora, **When** próbuje zmienić status konta lub rolę, **Then** system odmawia i nie zapisuje zmiany.

## 7. Pytania otwarte

Szczegóły, właściciele, status i odpowiadające Issues znajdują się w [otwartych kwestiach](12-otwarte-kwestie.md). Kwestie o największym wpływie na model: limit miejsc, termin anulowania zapisu, edycja terminu z zapisami, aktywacja kont, zakres dostępu administratora, forma konsultacji oraz retencja danych.

## 8. Priorytety MoSCoW

| Priorytet | Wymagania | Liczba |
|---|---|---:|
| Must | FR-01, FR-02, FR-03, FR-07, FR-08, FR-09, FR-10, FR-11, FR-14, FR-17 | 10 |
| Should | FR-04, FR-05, FR-06, FR-12, FR-13, FR-15, FR-16, FR-18 | 8 |
| Could | brak w obecnej wersji | 0 |
| Won't now | wideokonferencje, powiadomienia e-mail/SMS, SSO, integracja z planem zajęć, aplikacja natywna, rezerwacje cykliczne | poza FR v1 |

## 9. Aktualizacje po walkthrough procesów (zajęcia 5)

| Element | Zmiana | Powód / ślad |
|---|---|---|
| FR-08 | doprecyzowano atomową kontrolę dostępności w chwili zapisu | P-01.8; wcześniejszy podgląd listy nie gwarantuje wolnego miejsca |
| FR-14 | rozszerzono o jednoznaczny status powiązanych zapisów po odwołaniu terminu | P-02.6; student musi rozpoznać, dlaczego termin przestał obowiązywać |
| BR-10 | dodano regułę: zapis możliwy wyłącznie dla terminu aktywnego, przyszłego i z wolnym miejscem w chwili zatwierdzenia | P-01.8–P-01.10; nowa reguła do walidacji |


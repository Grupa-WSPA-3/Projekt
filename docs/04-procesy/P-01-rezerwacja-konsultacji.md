# P-01 — Przeglądanie i zapis na konsultację (TO-BE)

**Wersja:** 0.2 — proces główny  
**Właściciel procesu:** Maksym Tymoshenko  
**Uczestnicy / tory:** Student, System SKW  
**Cel:** umożliwić studentowi znalezienie aktualnego terminu i utworzenie pojedynczego aktywnego zapisu bez przekroczenia limitu miejsc.

## Zdarzenie początkowe

Student potrzebuje konsultacji i rozpoczyna przeglądanie dostępnych terminów.

## Wyniki procesu

- **Sukces:** student otrzymuje potwierdzenie i widzi swój aktywny zapis.
- **Brak dostępności:** system informuje o braku miejsca / nieaktualnym terminie i nie tworzy zapisu.
- **Duplikat:** system wykrywa istniejący aktywny zapis tej osoby i nie tworzy drugiego.
- **Inny błąd walidacji:** system odrzuca nieprawidłową próbę i podaje przyczynę.

## Uczestnicy

| Tor / rola | Odpowiedzialność |
|---|---|
| Student | przegląda, wybiera termin i inicjuje zapis |
| System SKW | wyszukuje i wyświetla dostępne terminy, waliduje dane, ponownie sprawdza limit, zapisuje rezerwację i pokazuje rezultat |

## Diagram BPMN 2.0

Źródło: [P-01-rezerwacja-konsultacji.bpmn](P-01-rezerwacja-konsultacji.bpmn)  
Eksport: [P-01-rezerwacja-konsultacji.svg](P-01-rezerwacja-konsultacji.svg)

## Kroki procesu i wymagania

| Krok | Tor | Czynność | Typ | Wymagania / reguły |
|---|---|---|---|---|
| P-01.1 | Student | rozpoczyna przeglądanie konsultacji | zadanie użytkownika | N-01, FR-03 |
| P-01.2 | Student | podaje kryteria filtrowania, np. wykładowcę i datę | zadanie użytkownika | N-02, FR-04, FR-05 |
| P-01.3 | System SKW | pobiera i prezentuje przyszłe, aktywne terminy z wolnymi miejscami | zadanie usługi | FR-03, BR-02, BR-06 |
| P-01.4 | Student | wybiera termin i sprawdza jego szczegóły | zadanie użytkownika | N-03, FR-06 |
| P-01.5 | Student | inicjuje zapis na wybrany termin | zadanie użytkownika | N-04, FR-07 |
| P-01.6 | System SKW | sprawdza, czy termin istnieje, jest aktywny i rozpoczyna się w przyszłości | zadanie usługi | FR-18, BR-01, BR-10 |
| P-01.7 | System SKW | sprawdza, czy student nie ma już aktywnego zapisu na ten termin | zadanie usługi | FR-09, BR-03 |
| P-01.8 | System SKW | ponownie i atomowo sprawdza dostępność miejsca w momencie zatwierdzania | zadanie usługi | FR-08, FR-18, BR-02, BR-10 |
| P-01.9 | System SKW | tworzy zapis i aktualizuje liczbę wolnych miejsc | zadanie usługi | FR-07, BR-02, BR-07 |
| P-01.10 | System SKW | pokazuje potwierdzenie i status zapisu | zadanie usługi | FR-16, FR-17 |
| P-01.11 | System SKW | odmawia zapisu, nie modyfikuje danych i przekazuje powód | zadanie usługi / wyjątek | FR-17, FR-18 |

## Bramki i wyjątki

| Bramka | Pytanie | Wyjście TAK | Wyjście NIE |
|---|---|---|---|
| G-01 | Czy termin istnieje, jest aktywny i przyszły? | kontynuuj do P-01.7 | odrzuć próbę — wynik „termin niedostępny” |
| G-02 | Czy student ma już aktywny zapis? | odrzuć jako duplikat | kontynuuj do P-01.8 |
| G-03 | Czy w chwili zatwierdzania pozostało wolne miejsce? | utwórz zapis P-01.9 | odrzuć próbę — wynik „brak miejsca” |

Co najmniej trzy ścieżki alternatywne w procesie głównym:

1. Termin anulowany, usunięty lub przeszły między wyświetleniem a zatwierdzeniem — G-01 = NIE.
2. Student ponawia zapis na termin, na którym już jest zapisany — G-02 = TAK.
3. Dwie osoby jednocześnie próbują zająć ostatnie miejsce — tylko jedna transakcja może przejść G-03; druga otrzymuje odmowę.
4. Niepoprawne lub niekompletne dane — system nie tworzy zapisu, pokazuje błąd walidacji.

## Reguły / ograniczenia procesu

- Samo wyświetlenie terminu nie rezerwuje miejsca.
- Dostępność musi zostać sprawdzona ponownie w chwili zatwierdzania.
- W bazie danych musi być zachowana integralność limitu; samo sprawdzenie w interfejsie nie wystarcza.
- Duplikat aktywnego zapisu jest niedozwolony.
- Status „potwierdzony” może zostać wyświetlony wyłącznie po trwałym utworzeniu zapisu.

## Otwarte pytania

- Czy zapis wymaga dodatkowego zatwierdzenia przez wykładowcę? (Q-01 / do potwierdzenia, jeśli dotyczy)
- Czy limit miejsc może być większy niż 1? (Q-02)
- Czy student może mieć nakładające się terminy u różnych wykładowców? (Q-09)
- Czy wymagane są dodatkowe dane przed zapisem? (Q-13)


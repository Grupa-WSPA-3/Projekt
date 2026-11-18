# Projekt interfejsu SKW — opis widoków

**Status:** zakres ekranów i przepływów; makiety graficzne do przygotowania w narzędziu wybranym przez zespół. Nie przedstawia gotowego prototypu.

## Student

1. Logowanie.
2. Lista dostępnych konsultacji z filtrem wykładowcy i daty.
3. Szczegóły terminu i liczba wolnych miejsc.
4. Potwierdzenie zapisu lub komunikat o odmowie.
5. Lista własnych zapisów i anulowanie zapisu.

## Wykładowca

1. Logowanie.
2. Lista własnych terminów.
3. Formularz utworzenia / edycji terminu.
4. Lista zapisanych studentów dla własnego terminu.
5. Potwierdzenie anulowania terminu i informacja o zmianie statusów zapisów.

## Administrator

1. Logowanie.
2. Lista kont.
3. Aktywacja / dezaktywacja konta.
4. Przypisanie podstawowej roli.

## Zasady UI wynikające z wymagań

- Pokazywać status terminu i liczbę wolnych miejsc przed rozpoczęciem rezerwacji.
- Nie oznaczać zapisu jako potwierdzonego przed odpowiedzią serwera i trwałym zapisem danych (FR-17).
- Przy braku miejsca wyświetlić komunikat, że inny użytkownik mógł zająć ostatnie miejsce.
- Oddzielić anulowanie zapisu przez studenta od anulowania całego terminu przez wykładowcę.
- Ukrywać funkcje niedostępne dla danej roli i dodatkowo egzekwować uprawnienia po stronie serwera.
- Podstawowe widoki zachować czytelne przy szerokościach 360, 768 i 1366 px (NFR-08).

## Kryteria do makiet

Każda makieta ma wskazaną rolę i cel. Dla odpowiednich ekranów należy przygotować stany: domyślny, ładowanie, brak danych, błąd i sukces. Komunikaty nie mogą sugerować powodzenia, jeżeli system odrzucił operację. Lista zapisów nie może być widoczna studentom ani wykładowcom niebędącym właścicielem terminu.

## Do wykonania

Makiety niskiej szczegółowości dla przepływów US-02, US-03, US-04 i US-05; następnie prototyp kluczowego przepływu zapisu. Miejsce/formę konsultacji doprecyzować po Q-07 i Q-13.

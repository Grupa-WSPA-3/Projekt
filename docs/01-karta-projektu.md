# Karta projektu — SKW

**Przedmiot:** Projekt zespołowy systemu informatycznego cz. 1  
**Wersja:** 0.4 — robocza  
**Status:** przygotowana na podstawie wersji 0.2 zespołu; do wspólnej weryfikacji i formalnego zatwierdzenia przez prowadzącego.

## 1. Podstawowe informacje

| Pole | Wartość |
|---|---|
| Pełna nazwa | System obsługi konsultacji wykładowców |
| Akronim | SKW |
| Typ systemu | system informatyczny wspierający organizację konsultacji na uczelni |
| Główna wartość | jeden aktualny widok terminów i zapisów oraz mniej ręcznej koordynacji |

### Zespół i podział odpowiedzialności

| Osoba | Główna odpowiedzialność | Obszary wspierane |
|---|---|---|
| Maksym Tymoshenko (`user123876t14987`) | koordynacja, analiza wymagań | procesy, integracja dokumentacji |
| Kostiantyn Kyrylenko (`Hryak123`) | model danych i architektura | wymagania techniczne, implementacja w kolejnym etapie |
| Sofiia Vetvytska (`miumeowww`) | UI/UX i dokumentacja | słownik, przegląd czytelności dokumentacji |
| Alina Semeniuk (`semenukalina89-maker`) | testowanie i kryteria akceptacji | bezpieczeństwo dostępu, macierz testów |

Koordynator pilnuje terminów i spójności pracy, ale nie jest przełożonym pozostałych osób. Podział jest propozycją roboczą i powinien być potwierdzony przez cały zespół.

## 2. Problem

Informacje o konsultacjach mogą być przekazywane przez pocztę elektroniczną, komunikatory lub ustnie. W takim rozwiązaniu trudno zachować jeden aktualny widok wolnych terminów, ograniczyć ryzyko nakładających się ustaleń i szybko sprawdzić, kto jest zapisany. Wykładowca samodzielnie kontroluje listę osób i przekazuje informacje o zmianie lub odwołaniu terminu. Student może nie wiedzieć, czy termin nadal jest aktualny.

Opis powyżej pochodzi z pierwotnej karty zespołu. Konkretne częstotliwości problemów i obecny sposób pracy na uczelni wymagają potwierdzenia podczas wywiadu.

## 3. Kogo dotyczy problem?

- **Studentów**, którzy chcą znaleźć konsultację i zarezerwować miejsce bez wymiany wielu wiadomości.
- **Wykładowców**, którzy chcą publikować terminy, kontrolować dostępność i widzieć listę zapisanych osób.
- **Administratora**, który zarządza kontami i rolami oraz pomaga utrzymać porządek w systemie.
- **Uczelni / dziekanatu**, dla których uporządkowany sposób zapisu może zmniejszyć liczbę ręcznych ustaleń.

## 4. Cel systemu

Celem SKW jest udostępnienie jednego miejsca do publikowania terminów konsultacji, sprawdzania ich dostępności, zapisywania studentów i anulowania zapisów. System ma ograniczyć ryzyko przekroczenia limitu miejsc, zapewniać kontrolę uprawnień i ułatwiać wykładowcom zarządzanie listą osób.

### Jak poznamy, że cel został osiągnięty?

1. Student może znaleźć przyszły dostępny termin i zapisać się bez kontaktowania się z wykładowcą poza systemem.
2. Przy próbie rezerwacji ostatniego miejsca przez dwie osoby tylko jedna rezerwacja zostaje potwierdzona.
3. Wykładowca może dodać termin oraz zobaczyć listę zapisanych studentów.
4. Student nie może anulować zapisu innej osoby ani zmieniać terminu wykładowcy.
5. Każde wymaganie Must ma kryteria akceptacji, a przed wydaniem zostaje sprawdzone.

Są to kryteria projektowe do weryfikacji, a nie wyniki przeprowadzonych testów.

## 5. Użytkownicy systemu

| Rola | Potrzeby | Główne uprawnienia |
|---|---|---|
| Student | znaleźć termin, sprawdzić dostępność i zarządzać własnym zapisem | przeglądanie terminów, rezerwacja, anulowanie własnego zapisu |
| Wykładowca | publikować terminy i kontrolować listę zapisów | tworzenie, edycja nieobsadzonego terminu, anulowanie własnej konsultacji, wgląd do własnej listy zapisów |
| Administrator | utrzymywać konta i role | zarządzanie kontami i przypisaniem ról; brak potrzeby przeglądania szczegółów zapisów, jeśli nie jest to konieczne |

## 6. Interesariusze

| Interesariusz | Interes / oczekiwana korzyść | Sposób uwzględnienia |
|---|---|---|
| Studenci | aktualna lista dostępnych konsultacji i prosty zapis | historyjki US dla przeglądania i rezerwacji |
| Wykładowcy | mniej ręcznej koordynacji i aktualna lista zapisanych osób | funkcje zarządzania terminami i listą zapisów |
| Administrator uczelni | kontrola kont i ról | ograniczone funkcje administracyjne |
| Dziekanat / jednostki dydaktyczne | sprawniejsza organizacja konsultacji | wynik końcowy może być oceniony na podstawie zasad i procesu |
| Prowadzący przedmiot | zgodność projektu z etapami dokumentacji i metodą pracy zespołowej | wersjonowane dokumenty, Issues, PR i recenzje |

## 7. Zakres IN — pierwsza wersja

1. Logowanie użytkowników z istniejącymi kontami SKW.
2. Rozróżnianie ról student, wykładowca i administrator.
3. Wyświetlanie przyszłych, aktywnych terminów konsultacji.
4. Wyszukiwanie / filtrowanie terminów według wykładowcy i daty.
5. Wyświetlanie szczegółów terminu, w tym daty, czasu, wykładowcy i miejsca/forma spotkania po potwierdzeniu tych pól.
6. Zapisywanie studenta na dostępny termin.
7. Kontrola limitu miejsc także w sytuacji równoczesnych prób zapisu.
8. Ochrona przed wielokrotnym aktywnym zapisem tej samej osoby na ten sam termin.
9. Anulowanie własnego zapisu przez studenta.
10. Tworzenie, edytowanie nieobsadzonych terminów i anulowanie własnych konsultacji przez wykładowcę.
11. Przeglądanie listy zapisanych studentów dla własnych konsultacji.
12. Wyświetlanie aktualnego statusu zapisu i wyniku operacji.
13. Zarządzanie kontami i rolami przez administratora.
14. Przechowywanie terminów, kont i zapisów oraz ich statusów.

Zakres funkcjonalny jest priorytetyzowany w `docs/03-wymagania.md` przez MoSCoW.

## 8. Zakres OUT — pierwsza wersja

- prowadzenie konsultacji przez wbudowaną wideokonferencję lub audio;
- obsługa ocen, egzaminów, zaliczeń i całego procesu dydaktycznego;
- wysyłka e-mail/SMS jako odrębny moduł powiadomień;
- zarządzanie pełnym planem zajęć uczelni i automatyczna synchronizacja z nim;
- płatności za konsultacje;
- natywna aplikacja mobilna;
- integracja z zewnętrznym SSO/katalogiem uczelnianym — wymaga osobnej decyzji;
- rezerwacje cykliczne — do rozważenia po potwierdzeniu potrzeby, na razie nie należą do pierwszej wersji.

## 9. Najważniejsze funkcje

**Priorytet podstawowy:** logowanie i role, przeglądanie aktywnych terminów, rezerwacja bez przekroczenia limitu, anulowanie własnego zapisu, tworzenie terminów przez wykładowcę oraz jasny komunikat o wyniku operacji.

**Funkcje dalszej kolejności:** zaawansowane filtrowanie, edycja terminu, zarządzanie kontami, historia statusów i dodatkowe ostrzeżenia.

## 10. Główne obiekty / dane

| Obiekt | Podstawowe informacje | Uwagi |
|---|---|---|
| Konto użytkownika | identyfikator, nazwa, dane niezbędne do logowania, rola, status konta | nie przechowywać zbędnych danych osobowych |
| Termin konsultacji | identyfikator, wykładowca, początek i koniec, miejsce/forma, limit miejsc, status | status i zasady edycji do zatwierdzenia |
| Zapis | identyfikator, student, termin, data zapisu, status | dla danego studenta i terminu tylko jeden aktywny zapis |
| Rola | student, wykładowca, administrator | określa uprawnienia |
| Lista zapisów | lista zapisów powiązana z terminem | dostępna wykładowcy tylko dla własnych terminów |

## 11. Główne założenia — do potwierdzenia

- System będzie aplikacją webową, a nie natywną aplikacją mobilną.
- Każdy użytkownik posiada konto i jedną podstawową rolę.
- Każdy wykładowca zarządza tylko własnymi terminami.
- Domyślny limit miejsc wynosi 1, ale model powinien umożliwiać ustawienie większej liczby dla konsultacji grupowej.
- Termin musi rozpoczynać się w przyszłości, a koniec musi być późniejszy niż początek.
- Termin z aktywnymi zapisami nie może być swobodnie przesuwany; w wersji podstawowej najpierw trzeba go anulować i utworzyć nowy.
- Nie wysyłamy automatycznych wiadomości e-mail/SMS w pierwszej wersji.
- W pierwszej wersji nie ma integracji z zewnętrznym planem zajęć ani SSO.
- Czas systemowy i wyświetlanie godzin przyjmują strefę `Europe/Warsaw` — wymaga potwierdzenia.

## 12. Wstępne ryzyka

Szczegółowy rejestr znajduje się w `docs/13-ryzyka.md`. Najważniejsze ryzyka: nieweryfikowane założenia o procesie, równoczesna rezerwacja ostatniego miejsca, niejasne zasady edycji/anulowania, ochrona danych osobowych i nierówny podział pracy.

## 13. Technologie i narzędzia

Decyzja ADR-001 dotyczy narzędzi pracy zespołowej, dokumentacji, diagramów, modelowania danych i makiet UI. **Technologia implementacji systemu (język, framework, baza danych i hosting) nie została na tym etapie zatwierdzona.** Nie wybieramy jej wyłącznie dlatego, że jest modna; należy najpierw domknąć analizę i architekturę.

## 14. Decyzje wymagające potwierdzenia

1. Czy temat został formalnie zaakceptowany przez prowadzącego?
2. Czy limit miejsc może być większy niż 1?
3. Czy student może anulować zapis do samego początku konsultacji?
4. Czy termin z zapisanymi studentami można edytować, czy wyłącznie anulować?
5. Kto zakłada konta oraz resetuje dostęp?
6. Czy konsultacja może być zdalna i czy potrzebny jest tylko tekstowy link do spotkania?
7. Czy potrzebne są konsultacje cykliczne?

Pytania i właściciele są ujęci w `docs/12-otwarte-kwestie.md`.

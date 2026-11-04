# KARTA PROJEKTU — WERSJA 0.3

## 1. Podstawowe informacje

**Nazwa projektu:** *System obsługi konsultacji wykładowców*

**Krótka nazwa / akronim:** SKW

**Zespół:**

| Imię i nazwisko | Rola główna | Kontakt / login repozytorium |
|---|---|---|
| Maksym Tymoshenko | koordynacja projektu, analiza wymagań | `@mtwspa` |
| Kostiantyn Kyrylenko | model danych, architektura | `@Hryak123` |
| Sofiia Vetvytska | UI/UX, dokumentacja | `@miumeowww` |
| Alina Semeniuk | testowanie, kryteria akceptacji | `@semenukalina89-maker` |

Podział ról jest propozycją roboczą do potwierdzenia przez zespół. Każdy członek może wspierać pozostałe obszary.

---

## 2. Problem

### Jaki problem chcemy rozwiązać?

Informacje o konsultacjach wykładowców mogą być przekazywane studentom różnymi kanałami, na przykład przez pocztę elektroniczną, komunikatory lub ustnie. Przy takim sposobie organizacji trudno utrzymać jeden aktualny widok dostępnych terminów i liczby wolnych miejsc. Uzgadnianie terminu oraz potwierdzanie zapisu może wymagać dodatkowej wymiany wiadomości między studentem a wykładowcą. Zespół zakłada, że brak wspólnego miejsca do publikowania terminów i obsługi zapisów może prowadzić do nieporozumień, dlatego ten problem wymaga potwierdzenia podczas wywiadu.

---

## 3. Kogo dotyczy problem?

Problem dotyczy przede wszystkim studentów, którzy chcą znaleźć dogodny termin konsultacji i zapisać się bez wielokrotnego kontaktowania się z wykładowcą. Dotyczy również wykładowców, którzy publikują terminy, ustalają limity miejsc i kontrolują listy zapisanych osób. Pośrednio dotyczy administratorów oraz jednostek uczelni odpowiedzialnych za organizację i wsparcie procesu konsultacji.

---

## 4. Cel systemu

> Celem systemu jest zapewnienie jednego miejsca do publikowania terminów konsultacji wykładowców, sprawdzania ich dostępności, zapisywania studentów i anulowania zapisów.

System powinien ograniczać ręczną koordynację, zapobiegać przekroczeniu limitu miejsc oraz umożliwiać wykładowcom zarządzanie własnymi terminami i listami zapisów. Osiągnięcie celu będzie można sprawdzić poprzez scenariusze przeglądania terminów, zapisu, anulowania oraz kontroli uprawnień.

---

## 5. Użytkownicy systemu

| Użytkownik / rola | Do czego będzie używał systemu? |
|---|---|
| Student | przeglądanie i filtrowanie terminów, sprawdzanie szczegółów, zapis i anulowanie własnego zapisu |
| Wykładowca | tworzenie, edytowanie i anulowanie własnych terminów oraz przeglądanie list zapisanych studentów |
| Administrator | zarządzanie kontami użytkowników i przypisanymi rolami |

---

## 6. Interesariusze

| Interesariusz | Dlaczego system jest dla niego istotny? |
|---|---|
| Studenci | chcą znaleźć aktualne terminy i zapisać się na konsultację bez dodatkowych ustaleń |
| Wykładowcy | chcą publikować terminy i kontrolować listę zapisanych osób w jednym miejscu |
| Administrator systemu | odpowiada za prawidłowe konta, role i dostęp do funkcji |
| Dziekanat / jednostki dydaktyczne | są zainteresowane sprawną organizacją konsultacji i ograniczeniem ręcznej koordynacji |
| Władze uczelni | mogą być zainteresowane uporządkowaniem procesu oraz przejrzystością organizacji konsultacji |

---

## 7. Zakres IN

Co system **będzie** realizował?

1. Umożliwienie logowania użytkownikom posiadającym aktywne konta.
2. Rozróżnianie ról: Student, Wykładowca i Administrator.
3. Wyświetlanie przyszłych, aktywnych terminów konsultacji.
4. Wyszukiwanie i filtrowanie terminów według wykładowcy oraz daty.
5. Wyświetlanie szczegółów terminu, w tym daty, godzin, wykładowcy, miejsca lub formy oraz limitu miejsc — po potwierdzeniu wymaganych pól.
6. Zapisywanie studenta na dostępny termin z kontrolą limitu miejsc i bez tworzenia duplikatu aktywnego zapisu.
7. Anulowanie własnego zapisu przez studenta.
8. Tworzenie i edytowanie przez wykładowcę własnych terminów, zgodnie z przyjętymi regułami.
9. Anulowanie własnego terminu przez wykładowcę oraz przeglądanie listy zapisanych studentów.
10. Zarządzanie kontami i rolami przez administratora oraz wyświetlanie statusu i wyniku operacji.

---

## 8. Zakres OUT

Czego system **nie będzie** realizował w pierwszej wersji?

1. Prowadzenia wideokonferencji lub rozmów audio.
2. Wysyłania automatycznych powiadomień e-mail lub SMS.
3. Zarządzania pełnym planem zajęć dydaktycznych.
4. Automatycznej synchronizacji z uczelnianym systemem planu zajęć.
5. Integracji z zewnętrznym systemem SSO lub katalogiem użytkowników.
6. Obsługi płatności, ocen, egzaminów ani innych procesów dydaktycznych.
7. Natywnej aplikacji mobilnej i rezerwacji cyklicznych.

---

## 9. Najważniejsze funkcje

1. Logowanie użytkownika i dostęp zgodny z przypisaną rolą.
2. Przeglądanie przyszłych dostępnych terminów konsultacji.
3. Wyszukiwanie i filtrowanie konsultacji według wykładowcy i daty.
4. Wyświetlanie szczegółów terminu i liczby wolnych miejsc.
5. Zapis studenta na termin z kontrolą dostępności i limitu miejsc.
6. Anulowanie własnego zapisu przez studenta.
7. Tworzenie i edycja własnych terminów przez wykładowcę.
8. Anulowanie własnego terminu przez wykładowcę.
9. Przeglądanie przez wykładowcę listy studentów zapisanych na jego termin.
10. Zarządzanie kontami i rolami oraz prezentowanie statusu operacji przez system.

---

## 10. Główne obiekty / dane

1. **Konto użytkownika** — identyfikator konta, dane niezbędne do logowania i status konta.
2. **Rola** — określenie uprawnień użytkownika: Student, Wykładowca lub Administrator.
3. **Termin konsultacji** — wykładowca, początek i koniec, miejsce lub forma, limit miejsc i status.
4. **Zapis** — powiązanie studenta z terminem, data wykonania operacji i status zapisu.
5. **Lista zapisów / historia statusów** — zestaw zapisów powiązanych z terminem oraz informacja, czy zapis lub termin został anulowany.

---

## 11. Główne założenia

- System będzie aplikacją webową; natywna aplikacja mobilna nie należy do pierwszej wersji.
- Każdy użytkownik posiada konto i jedną podstawową rolę.
- Wykładowca zarządza wyłącznie własnymi terminami i listami zapisów.
- Domyślny limit miejsc wynosi 1; możliwość konsultacji grupowych wymaga potwierdzenia.
- Termin musi rozpoczynać się w przyszłości, a jego koniec musi być późniejszy niż początek.
- W pierwszej wersji nie zakłada się integracji z SSO, planem zajęć ani zewnętrznym serwerem powiadomień.
- Założenia wynikające z braku rzeczywistego protokołu wywiadu muszą zostać zweryfikowane przed uznaniem wymagań za ostateczne.

---

## 12. Wstępne ryzyka

| Ryzyko | Dlaczego może być problemem? |
|---|---|
| Niepotwierdzony sposób organizacji konsultacji | założenia zespołu mogą nie odpowiadać rzeczywistemu procesowi na uczelni |
| Równoczesna próba zapisu na ostatnie miejsce | bez właściwej kontroli system mógłby potwierdzić zbyt wiele zapisów |
| Niejasne zasady anulowania i edycji terminów | mogą powstać niespójne statusy terminów i zapisów |
| Nieprawidłowe uprawnienia do list zapisów | dane studentów mogłyby być widoczne dla nieuprawnionych osób |
| Zbyt szeroki zakres pierwszej wersji | dodawanie integracji i powiadomień może utrudnić ukończenie projektu w semestrze |

Szczegółowy rejestr ryzyk znajduje się w `docs/13-ryzyka.md`.

---

## 13. Wstępnie rozważane technologie

Ta część nie oznacza zatwierdzenia stosu technologicznego aplikacji. Wybór implementacji powinien nastąpić po dalszej analizie procesów, danych i architektury.

**Frontend:** nie wybrano — do decyzji na późniejszym etapie.

**Backend:** nie wybrano — do decyzji na późniejszym etapie.

**Baza danych:** nie wybrano — do decyzji na późniejszym etapie.

**Inne:** do dokumentacji i współpracy zespołu proponuje się GitHub, Markdown, Mermaid oraz diagrams.net; decyzje dotyczące narzędzi pracy opisuje ADR-001.

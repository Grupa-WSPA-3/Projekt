# Lista kandydatów „make or buy” — SKW

**Wersja:** 0.1 · **Status:** wstępna lista do zajęć 6 · **Decyzje technologiczne:** niezatwierdzone

## Cel
Wskazać funkcje SKW, które zespół powinien zaprojektować i wykonać samodzielnie (make) oraz elementy, dla których można rozważyć gotowe rozwiązanie (buy). To lista kandydatów, a nie zatwierdzony wybór produktów, dostawców ani technologii.

## Kandydaci

| Funkcja / wymaganie | Kandydat rozwiązania | Wstępnie | Uzasadnienie / pytanie do sprawdzenia |
|---|---|---|---|
| Logowanie aktywnego konta (FR-01) | Mechanizm kont i logowania w SKW; uczelniane SSO wyłącznie jako ewentualna przyszła integracja | make w v1; buy jako przyszły wariant | SSO jest poza zakresem pierwszej wersji. Jak uczelnia tworzy i aktywuje konta? (Q-05, Q-12) |
| Kontrola ról i uprawnień (FR-02, FR-15; BR-04, BR-08, BR-09) | Reguły uprawnień w SKW | make | Uprawnienia są związane z rolami Student, Wykładowca i Administrator. Czy konto może mieć więcej niż jedną rolę? (Q-05) |
| Lista terminów, wyszukiwanie i szczegóły (FR-03…FR-06) | Funkcje aplikacji SKW; ewentualna biblioteka komponentu kalendarza / wyboru dat | make; komponent UI do decyzji | Nie wskazano konkretnej biblioteki ani produktu. Czy konsultacje wymagają widoku kalendarza, czy wystarczy lista? |
| Zapis, limit miejsc i ochrona przed duplikatem (FR-07…FR-09, FR-18; BR-02, BR-03) | Logika domenowa SKW i kontrola współbieżności | make | To podstawowa logika projektu. Jakie limity miejsc obowiązują dla konsultacji grupowych? (Q-02) |
| Anulowanie własnego zapisu (FR-10; BR-07) | Logika statusu zapisu w SKW | make | Zmiana statusu oraz zwolnienie miejsca są częścią podstawowego procesu P-03. Do kiedy można anulować zapis? (Q-03) |
| Tworzenie, edycja i anulowanie terminów (FR-11, FR-12, FR-14; BR-01, BR-05, BR-06) | Logika zarządzania terminami w SKW | make | Reguły własności terminu i aktywnych zapisów stanowią część domeny SKW. Czy termin z zapisami może być wyjątkowo edytowany? (Q-04) |
| Lista zapisów wykładowcy (FR-13; BR-08) | Widok listy w SKW | make | Dostęp do danych studentów musi być ograniczony do uprawnionej roli. Czy administrator powinien mieć taki wgląd? (Q-06) |
| Statusy i komunikaty w aplikacji (FR-16, FR-17) | Komunikaty wewnątrz aplikacji SKW | make | Automatyczne powiadomienia e-mail/SMS są poza zakresem v1. Czy w przyszłości będą potrzebne? |
| Integracja z pocztą e-mail / SMS | Zewnętrzna usługa powiadomień | buy — poza v1 | Nie implementować w obecnej wersji. Rozważyć dopiero po zmianie zakresu i ustaleniu wymagań. |
| Integracja z uczelnianym SSO | Uczelniany dostawca tożsamości | buy — poza v1 | Nie jest częścią bieżącej granicy systemu. Wymaga potwierdzenia dostępności i zasad integracji. |
| Synchronizacja z planem zajęć | System planu zajęć uczelni / interfejs integracyjny | buy — poza v1 | Automatyczna synchronizacja została wyłączona z zakresu pierwszej wersji. |

## Wstępny podział
- **Make (v1):** logowanie w zakresie obecnej funkcjonalności, role, lista i szczegóły terminów, zapisy, kontrola limitu, anulowanie zapisu, zarządzanie terminami, lista zapisów oraz statusy w aplikacji.
- **Buy (kandydaci przyszłości):** SSO uczelni, usługa e-mail/SMS i integracja z systemem planu zajęć — wszystkie pozostają poza bieżącym zakresem.
- **Do decyzji:** ewentualna biblioteka komponentu kalendarza / wyboru dat; nie wskazano konkretnego produktu.

## Ograniczenia i kolejne kroki
1. Nie wybrano technologii frontend, backend ani bazy danych — lista nie zatwierdza żadnego stosu technologicznego.
2. Nie zakładamy mikroserwisów, Dockera ani konkretnej infrastruktury na podstawie tej listy.
3. Na zajęciach 6 należy porównać kandydatów z realną ofertą i zapisać uzasadnione decyzje jako ADR.
4. Każda zmiana integracji z SSO, pocztą lub planem zajęć wymaga ponownego sprawdzenia zakresu IN/OUT w karcie projektu.

# Otwarte kwestie i decyzje do potwierdzenia

**Wersja:** 0.1 — robocza  
**Zasada:** pytanie, które wpływa na zakres lub reguły biznesowe, ma właściciela i osobne GitHub Issue. Nie wpisujemy fikcyjnego numeru Issue, dopóki nie zostanie utworzone na GitHubie.

| ID | Pytanie / decyzja | Dlaczego ma znaczenie | Właściciel | Status | GitHub Issue |
|---|---|---|---|---|
| Q-01 | Czy temat SKW został formalnie zaakceptowany przez prowadzącego? | określa, czy możemy kontynuować temat bez zmiany zakresu | Maksym Tymoshenko | do potwierdzenia | [#21](https://github.com/Grupa-WSPA-3/Projekt/issues/21) |
| Q-02 | Czy konsultacje mogą mieć limit miejsc większy niż 1? | wpływa na model terminu i logikę rezerwacji | Kostiantyn Kyrylenko | do potwierdzenia | [#14](https://github.com/Grupa-WSPA-3/Projekt/issues/14) |
| Q-03 | Do kiedy student może anulować własny zapis? | określa regułę biznesową i kryterium akceptacji | Maksym Tymoshenko | do potwierdzenia | [#15](https://github.com/Grupa-WSPA-3/Projekt/issues/15) |
| Q-04 | Czy termin z aktywnymi zapisami można edytować? | wpływa na historię zapisów i informowanie studentów | Kostiantyn Kyrylenko | do potwierdzenia | [#16](https://github.com/Grupa-WSPA-3/Projekt/issues/16) |
| Q-05 | Kto tworzy konto i w jaki sposób można odzyskać dostęp? | wpływa na zakres logowania i bezpieczeństwo | Alina Semeniuk | do potwierdzenia | [#22](https://github.com/Grupa-WSPA-3/Projekt/issues/22) |
| Q-06 | Czy administrator potrzebuje wglądu do list studentów zapisanych na konsultację? | dotyczy minimalizacji danych i autoryzacji | Alina Semeniuk | do potwierdzenia | [#17](https://github.com/Grupa-WSPA-3/Projekt/issues/17) |
| Q-07 | Czy konsultacje są stacjonarne, zdalne czy oba typy? | określa pola terminu, bez dodawania wideokonferencji | Sofiia Vetvytska | do potwierdzenia | [#23](https://github.com/Grupa-WSPA-3/Projekt/issues/23) |
| Q-08 | Czy są potrzebne konsultacje cykliczne? | potencjalnie poszerza zakres i model danych | Sofiia Vetvytska | poza pierwszą wersją; sprawdzić potrzebę | [#24](https://github.com/Grupa-WSPA-3/Projekt/issues/24) |
| Q-09 | Czy student może mieć dwa aktywne zapisy na nakładające się godziny u różnych wykładowców? | określa dodatkową regułę biznesową | Maksym Tymoshenko | do potwierdzenia; brak blokady w obecnych FR | [#18](https://github.com/Grupa-WSPA-3/Projekt/issues/18) |
| Q-10 | Czy strefa `Europe/Warsaw` jest właściwa dla wszystkich użytkowników? | wpływa na wyświetlanie i walidację godzin | Kostiantyn Kyrylenko | założenie robocze | [#25](https://github.com/Grupa-WSPA-3/Projekt/issues/25) |
| Q-11 | Jak długo przechowywać anulowane terminy i zapisy? | wpływa na prywatność i retencję danych | Alina Semeniuk | do potwierdzenia | [#20](https://github.com/Grupa-WSPA-3/Projekt/issues/20) |
| Q-12 | Czy w przyszłości potrzebna będzie integracja z SSO lub planem zajęć uczelni? | zmienia architekturę; obecnie jest poza zakresem | Maksym Tymoshenko | nie w v1; zapisać jako przyszłe rozszerzenie | [#26](https://github.com/Grupa-WSPA-3/Projekt/issues/26) |
| Q-13 | Jakie dane kontaktowe lub lokalizacyjne są obowiązkowe przy terminie? | wpływa na słownik i interfejs | Sofiia Vetvytska | do potwierdzenia | [#19](https://github.com/Grupa-WSPA-3/Projekt/issues/19) |
| Q-14 | Czy status „obecność” / odbyte spotkanie należy rejestrować? | może dodać nową rolę lub funkcję | Alina Semeniuk | poza zakresem bieżącej wersji | [#27](https://github.com/Grupa-WSPA-3/Projekt/issues/27) |

## Jak rozstrzygać

1. Każde pytanie zamienić w Issue z etykietą `pytanie-do-klienta`, jednym właścicielem i kontekstem.
2. Odpowiedź skopiować do tego pliku oraz do źródłowego dokumentu (wywiad, wymagania, słownik lub karta).
3. Jeśli odpowiedź zmienia regułę lub wymaganie, dodać zmianę w tym samym PR i zaktualizować macierz śledzenia.
4. Jeśli odpowiedzi brak, zachować status „otwarte” i opisać bezpieczne założenie oraz wpływ na zakres.

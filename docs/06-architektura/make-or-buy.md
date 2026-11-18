# Kandydaci do analizy make-or-buy

**Cel:** wskazać obszary, w których można wykorzystać gotowe narzędzie lub usługę zamiast projektować całość samodzielnie. To lista kandydatów, nie zatwierdzone decyzje ani deklaracja zakupu.

| Funkcja / wymaganie | Kandydat gotowy | Wstępna ocena | Uzasadnienie | Pytanie do sprawdzenia |
|---|---|---|---|---|
| Uwierzytelnianie / logowanie (FR-01) | biblioteka uwierzytelniania lub SSO uczelni w przyszłości | do decyzji; SSO poza v1 | bezpieczeństwo logowania jest ważne, ale integracja z systemem uczelni nie jest potwierdzona | czy uczelnia udostępnia SSO i czy projekt ma do niego dostęp? |
| Wysyłka e-mail/SMS | serwer pocztowy uczelni lub zewnętrzna usługa powiadomień | Won't now / kandydat przyszły | automatyczne powiadomienia są poza pierwszą wersją | czy powiadomienia są wymagane i czy wolno użyć usług zewnętrznych? |
| Kalendarz / widok terminów | gotowy komponent kalendarza webowego | buy / open source do oceny | komponent może ograniczyć nakład pracy UI, nie zmieniając reguł biznesowych | czy licencja pozwala wykorzystać komponent w projekcie i czy spełnia wymagania dostępności? |
| Baza danych | relacyjny silnik open source, np. PostgreSQL | buy / wykorzystać gotowy silnik | system wymaga spójnych relacji i transakcyjnej kontroli limitu miejsc | jakie środowisko zapewni uczelnia / prowadzący i jakie są wymagania wdrożeniowe? |
| Rdzeń rezerwacji i reguły limitu (FR-07…FR-10, BR-02…BR-03) | brak gotowego rozwiązania domenowego | make | to podstawowa logika odróżniająca SKW; wymaga własnych reguł oraz testów współbieżności | jak zagwarantować atomowość zapisu i brak przekroczenia limitu? |
| Projekt interfejsu | Penpot lub Figma | buy / narzędzie wspierające | wykorzystanie gotowego narzędzia projektowego, a nie tworzenie własnego edytora | jakie narzędzie jest dostępne wszystkim członkom zespołu? |
| Dokumentacja i backlog | GitHub, Issues i Projects | buy / istniejąca platforma | repozytorium już jest używane przez zespół i wiąże dokumenty z zadaniami i PR | czy każdy członek zespołu ma dostęp do Projects i może aktualizować statusy? |

## Zasada podejmowania decyzji

Decyzję podejmować po sprawdzeniu kosztu, licencji, bezpieczeństwa, integracji, dostępności i ograniczeń technicznych. Zatwierdzoną decyzję zapisać jako osobny ADR. Obecny plik jest listą kandydatów przygotowaną do dalszej analizy.


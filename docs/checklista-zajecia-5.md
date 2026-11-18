# Checklista zgodności dokumentacji z materiałami do zajęć 5

**Projekt:** SKW — System obsługi konsultacji wykładowców  
**Stan:** PR #29, gałąź `docs/dokumentacja-analityczna`  
**Cel:** szybka autokontrola kompletności artefaktów wskazanych w materiałach prowadzącego do zajęć 5 i przygotowania na kolejne spotkanie.

Legenda: **Gotowe w dokumentacji** = artefakt istnieje w repozytorium; **Do potwierdzenia** = wymaga rzeczywistego źródła / działania zespołu; **Do wykonania w GitHub** = wymaga ustawienia poza plikami dokumentacji.

## 1. Wymagania 0.2 — część wejściowa

| Kryterium | Stan | Miejsce / uwagi |
|---|---|---|
| `docs/03-wymagania.md` w wersji 0.2 | Gotowe w dokumentacji | [03-wymagania.md](03-wymagania.md) |
| FR mają priorytety MoSCoW | Gotowe w dokumentacji | 18 FR: 10 Must, 8 Should |
| NFR są przypisane do kategorii ISO/IEC 25010 | Gotowe w dokumentacji | 8 mierzalnych NFR, kategorie modelu 2023; Safety rozważone i oznaczone jako nieadekwatne do zakresu |
| Co najmniej 5 reguł biznesowych | Gotowe w dokumentacji | BR-01…BR-10 |
| Wszystkie historyjki Must mają GWT | Gotowe w dokumentacji | US-01…US-05; osobne US-06 dla wykładowcy i US-07 dla administratora |
| Backlog GitHub Projects | Do potwierdzenia w GitHub | Dostępne pliki dokumentacji i Issues; aktywność / grupowanie widoku Projects trzeba sprawdzić w interfejsie projektu |
| Macierz potrzeba → wymaganie → historyjka | Gotowe w dokumentacji | [macierz-sledzenia.md](macierz-sledzenia.md), wersja 0.3 |
| Zmiany przez PR z recenzją | PR otwarty, review oczekuje | [PR #29](https://github.com/Grupa-WSPA-3/Projekt/pull/29); poproszono o review @Hryak123, nie oznaczono review jako wykonanego |
| Notatki AS-IS: kroki, role, narzędzia i punkty bólu | Gotowe jako hipoteza do walidacji | [P-00 AS-IS](04-procesy/P-00-as-is-notatki.md); rzeczywiste szczegóły muszą być potwierdzone w wywiadzie |

## 2. Procesy biznesowe AS-IS / TO-BE

| Kryterium | Stan | Miejsce / uwagi |
|---|---|---|
| Katalog `docs/04-procesy/` z README | Gotowe w dokumentacji | [README procesów](04-procesy/README.md) |
| Jeden proces AS-IS z tabelą kroków i punktami bólu | Gotowe jako hipoteza do walidacji | P-00, 6 kroków; narzędzia i kanały mają status „do potwierdzenia” |
| 2–3 procesy TO-BE | Gotowe w dokumentacji | P-01, P-02 i P-03 |
| Główny TO-BE w BPMN 2.0 — źródło + eksport SVG | Gotowe w dokumentacji | [P-01 BPMN](04-procesy/P-01-rezerwacja-konsultacji.bpmn) + [P-01 SVG](04-procesy/P-01-rezerwacja-konsultacji.svg) |
| AS-IS ma diagram i eksport | Gotowe jako hipoteza do walidacji | [P-00 BPMN](04-procesy/P-00-rezerwacja-as-is.bpmn) + [P-00 SVG](04-procesy/P-00-rezerwacja-as-is.svg) |
| Tory odpowiadają rolom; system ma osobny tor | Gotowe w P-01 | Student i System SKW; jedna pula „Uczelnia” |
| Systemy zewnętrzne jako pule | Nie dotyczy modelowanego v1 | SSO, system planu zajęć oraz automatyczna poczta są poza zakresem v1; nie pokazano niezatwierdzonych integracji |
| Podpisane warunki wyjść bramek i osobne wyniki końcowe | Gotowe w BPMN P-00 i P-01 | P-01: termin niedostępny, duplikat, brak miejsca, zapis potwierdzony |
| Co najmniej 3 wyjątki w głównym procesie | Gotowe w P-01 | nieaktualny termin, duplikat, wyścig o ostatnie miejsce / brak dostępności |
| Kroki P-xx.n i powiązania z FR | Gotowe w dokumentacji | P-01.1…P-01.13, P-02.1…P-02.8, P-03.1…P-03.6 |
| Kolumna „Proces” w macierzy dla wszystkich FR | Gotowe w dokumentacji | FR-15 ma jawne „—” z uzasadnieniem braku procesu administracyjnego w bieżącym zestawie |
| Co najmniej 2 nowe / uzupełnione FR/BR z walkthrough | Gotowe w treści PR | FR-08 i FR-14 doprecyzowane; dodano BR-10 |
| Lista kandydatów make-or-buy | Gotowe w dokumentacji | [make-or-buy.md](06-architektura/make-or-buy.md) |

## 3. GitHub — etykiety, kamienie milowe i review

| Kryterium | Stan | Uwagi |
|---|---|---|
| Otwarte Issues mają etykiety i właścicieli | Skonfigurowane wcześniej; wymaga końcowej kontroli | sprawdzić nowe / zmienione Issues przed oceną |
| Etykiety z listy prowadzącego | Do sprawdzenia w repozytorium | wymagane m.in. `wymagania`, `procesy`, `architektura`, `dane`, `ui`, `testy`, `pytanie-do-klienta` |
| Milestones M1, M2, M3 utworzone i przypisane do każdego otwartego Issue | Do wykonania w GitHub | nazwy: `M1 — Specyfikacja wymagań` (zajęcia 7), `M2 — Projekt techniczny` (zajęcia 11), `M3 — Projekt kompletny` (zajęcia 14). Nie wpisano dat kalendarzowych, bo materiały podają tylko numery zajęć. |
| PR sprawdzony przez inną osobę | Oczekuje na review | nie zamykać Issues i nie scalać PR przed faktycznym review |

## 4. Źródła i ograniczenia

W dostępnych archiwach nie znaleziono rzeczywistego protokołu wywiadu z odpowiedziami klienta i cytatami. Dlatego P-00, potrzeby i część BR są oznaczone jako hipotezy. To nie jest potwierdzenie, że każdy kanał (e-mail, telefon, komunikator, kalendarz, arkusz) faktycznie jest używany w organizacji. Należy zastąpić te hipotezy faktami wyłącznie na podstawie notatek z rozmowy lub dokumentów źródłowych.

Dokumentacja przedstawia artefakty analityczne i szkice wejściowe. Nie twierdzi, że system został zaimplementowany, testy wykonane ani makiety / modele kolejnych etapów ukończone.

## 5. Najważniejsze działania przed oddaniem

1. Poprosić członka zespołu niebędącego autorem o review [PR #29](https://github.com/Grupa-WSPA-3/Projekt/pull/29).
2. Utworzyć M1–M3 i przypisać wszystkie otwarte Issues.
3. Uzupełnić protokół P-00 rzeczywistymi ustaleniami, jeśli zespół posiada notatki z wywiadu; w przeciwnym razie jawnie przedstawić AS-IS jako hipotezę do walidacji.

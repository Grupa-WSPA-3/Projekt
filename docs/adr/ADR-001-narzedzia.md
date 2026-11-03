# ADR-001: Narzędzia pracy projektowej


## Kontekst

Zespół SKW składa się z czterech osób o różnych głównych odpowiedzialnościach: koordynacji i analizie wymagań, modelowaniu danych i architekturze, UI/UX i dokumentacji oraz testowaniu. Projekt wymaga wspólnego repozytorium, wersjonowanej dokumentacji, tablicy zadań z właścicielami, diagramów oraz przeglądu zmian przez Pull Request. Narzędzia powinny być dostępne dla wszystkich członków zespołu i umożliwiać zachowanie rezultatów w repozytorium na kolejnych etapach przedmiotu.

Poniższe oceny i wybory są propozycją roboczą. Zespół powinien je wspólnie sprawdzić i zmienić status ADR na „przyjęta” dopiero po akceptacji.

## Rozważane opcje

Wagi: 1 — mała ważność, 3 — duża ważność. Oceny: 1–5. Wynik ważony = ocena × waga. Punkty nie są obiektywnym pomiarem — służą do uporządkowania dyskusji.

### 1. Zarządzanie zadaniami — GitHub Projects vs Trello

| Kryterium | Waga | GitHub Projects | Trello |
|---|---:|---:|---:|
| Integracja z repozytorium i Issues | 3 | 5 (15) | 2 (6) |
| Próg wejścia | 2 | 4 (8) | 5 (10) |
| Dostępność do pracy kursowej | 3 | 5 (15) | 5 (15) |
| Historia, śledzenie wymagań i PR | 3 | 5 (15) | 2 (6) |
| **Suma ważona** | **11** | **53** | **37** |

**Propozycja:** GitHub Issues + Projects, ponieważ zadania można powiązać z plikami, commitami i PR. Wadą jest większy próg wejścia niż w prostej tablicy Trello.

### 2. Diagramy UML / BPMN — diagrams.net vs Mermaid

| Kryterium | Waga | diagrams.net | Mermaid |
|---|---:|---:|---:|
| Edycja źródła i przechowywanie w repozytorium | 3 | 3 (9) | 5 (15) |
| Wygoda tworzenia rozbudowanych diagramów | 3 | 5 (15) | 2 (6) |
| Próg wejścia | 2 | 4 (8) | 5 (10) |
| Dostępność bez opłat | 2 | 5 (10) | 5 (10) |
| **Suma ważona** | **10** | **42** | **41** |

**Propozycja:** Mermaid dla diagramu kontekstu i prostych diagramów tekstowych, a diagrams.net dla bardziej rozbudowanych diagramów BPMN/UML. Pliki `.drawio` powinny być przechowywane w repozytorium; eksport PNG lub SVG może służyć do podglądu.

### 3. Model danych — Mermaid ER vs dbdiagram.io

| Kryterium | Waga | Mermaid ER | dbdiagram.io |
|---|---:|---:|---:|
| Źródło zapisane bezpośrednio w repozytorium | 3 | 5 (15) | 3 (9) |
| Możliwość pokazania relacji i ograniczeń | 3 | 3 (9) | 5 (15) |
| Próg wejścia | 2 | 5 (10) | 3 (6) |
| Możliwość pracy bez zależności od konta | 2 | 5 (10) | 4 (8) |
| **Suma ważona** | **10** | **44** | **38** |

**Propozycja:** rozpocząć od Mermaid ER w Markdown. Jeżeli model będzie wymagał bardziej szczegółowych ograniczeń lub eksportu do innych narzędzi, ponownie ocenić dbdiagram.io.

### 4. Projekt interfejsu — Penpot vs Figma

| Kryterium | Waga | Penpot | Figma |
|---|---:|---:|---:|
| Eksport możliwy do dołączenia do repozytorium | 3 | 4 (12) | 4 (12) |
| Współpraca nad makietą | 3 | 4 (12) | 5 (15) |
| Próg wejścia | 2 | 3 (6) | 4 (8) |
| Dostępność rozwiązania open source / planu bez opłat | 3 | 5 (15) | 3 (9) |
| **Suma ważona** | **11** | **45** | **44** |

**Propozycja:** Penpot jako rozwiązanie open source. Makiety należy zachować w formacie źródłowym oraz dołączyć eksport SVG/PNG. Jeśli zespół zdecyduje się na Figma z uwagi na doświadczenie, powinien uzasadnić tę zmianę.

## Decyzja

Poniższa tabela przedstawia proponowany zestaw narzędzi. Wybór pozostaje propozycją do wspólnego zatwierdzenia.

| Obszar | Narzędzie | Format plików w repozytorium |
|---|---|---|
| repozytorium | GitHub | pliki projektu, historia commitów, Pull Requests |
| zadania | GitHub Issues + GitHub Projects | zadania i backlog w repozytorium / projekcie GitHub, z przypisanymi właścicielami |
| dokumentacja | Markdown | pliki `.md` |
| diagramy UML / BPMN | Mermaid i diagrams.net | `.md` z blokami Mermaid; `.drawio` oraz eksport `.png` / `.svg` |
| model danych | Mermaid ER na początek; ewentualnie dbdiagram.io po ponownej ocenie | `.md` z kodem Mermaid; dodatkowo eksport, jeżeli będzie potrzebny |
| interfejs | Penpot | pliki źródłowe projektu oraz eksporty `.svg` / `.png` |
| komunikacja | wspólny komunikator zespołu — narzędzie do potwierdzenia | istotne decyzje, pytania i ustalenia zapisywane dodatkowo w GitHub Issues oraz ADR |

## Konsekwencje

### Co zyskujemy

- Wspólną historię zmian oraz możliwość sprawdzenia wkładu poszczególnych członków zespołu.
- Powiązanie zadań z wymaganiami, commitami i Pull Requests.
- Możliwość przechowywania większości dokumentacji i diagramów bezpośrednio w repozytorium.
- Wykorzystanie narzędzi open source lub rozwiązań dostępnych bez zakupu licencji na potrzeby projektu.

### Co tracimy / jakie są ryzyka

- GitHub Projects wymaga krótkiego wdrożenia i przyzwyczajenia się do pracy z Issues.
- Mermaid jest mniej wygodny przy złożonych diagramach BPMN/UML niż edytor graficzny.
- Makiety interfejsu wymagają eksportu, aby można je było łatwo przeglądać bez otwierania narzędzia.
- Dostępność bezpłatnych planów i funkcji usług zewnętrznych może się zmienić.

### Co musimy zrobić

- Koordynator przygotuje tablicę GitHub Projects oraz podstawowe etykiety.
- Każdy członek zespołu powinien potwierdzić dostęp do wybranych narzędzi i przyjąć co najmniej jedno Issue.
- Zespół powinien wspólnie zatwierdzić lub skorygować proponowane oceny i wybór narzędzi.
- Po akceptacji należy uzupełnić datę przyjęcia decyzji i zmienić status ADR na „przyjęta”.
- Każda późniejsza zmiana narzędzia powinna zostać uzasadniona w nowej decyzji ADR.

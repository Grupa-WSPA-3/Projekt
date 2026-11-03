# ADR-001: Narzędzia pracy projektowej

**Status:** proponowana — wymaga potwierdzenia przez zespół  
**Autorzy:** zespół SKW  
**Zakres decyzji:** narzędzia pracy zespołu; nie jest to wybór technologii aplikacji końcowej.

## 1. Kontekst

Zespół składa się z czterech osób o różnych głównych odpowiedzialnościach: koordynacja i analiza, model danych, UI/UX i dokumentacja, testowanie. Wymagania przedmiotu zakładają dokumentację w repozytorium, widoczną historię zmian, zadania z właścicielami, diagramy oraz pracę przez Pull Request z recenzją. Narzędzia powinny mieć niski próg wejścia i pozwalać zachować rezultaty pracy w repozytorium na dalsze zajęcia.

## 2. Kryteria i wagi

Skala wagi: 1 — mniejsza ważność, 3 — duża ważność. Ocena opcji: 1–5. Wynik ważony = ocena × waga; nie jest to wynik obiektywny, lecz punkt wyjścia do dyskusji.

### 2.1. Zarządzanie zadaniami — GitHub Projects vs Trello

| Kryterium | Waga | GitHub Projects | Trello |
|---|---:|---:|---:|
| Integracja z repozytorium i Issues | 3 | 5 (15) | 2 (6) |
| Próg wejścia | 2 | 4 (8) | 5 (10) |
| Dostęp bez opłat dla pracy kursowej | 3 | 5 (15) | 5 (15) |
| Historia, śledzenie wymagań i PR | 3 | 5 (15) | 2 (6) |
| **Suma ważona** | **11** | **53** | **37** |

**Propozycja:** GitHub Issues + Projects, ponieważ zadania można powiązać z plikami, commitami i PR. Wadą jest większy próg wejścia niż w prostej tablicy Trello.

### 2.2. Diagramy UML/BPMN — diagrams.net vs Mermaid

| Kryterium | Waga | diagrams.net | Mermaid |
|---|---:|---:|---:|
| Edycja źródła i przechowywanie w repozytorium | 3 | 3 (9) | 5 (15) |
| Wygoda rysowania BPMN/UML | 3 | 5 (15) | 2 (6) |
| Próg wejścia | 2 | 4 (8) | 5 (10) |
| Dostępność bez opłat | 2 | 5 (10) | 5 (10) |
| **Suma ważona** | **10** | **42** | **41** |

**Propozycja:** używać Mermaid dla diagramu kontekstu i prostych diagramów tekstowych, a diagrams.net dla BPMN/UML, kiedy potrzebne są bogatsze symbole. Pliki `.drawio` należy przechowywać w repozytorium, a do przeglądu dołączyć eksport PNG/SVG.

### 2.3. Model danych — Mermaid ER vs dbdiagram.io

| Kryterium | Waga | Mermaid ER | dbdiagram.io |
|---|---:|---:|---:|
| Źródło zapisane bezpośrednio w repozytorium | 3 | 5 (15) | 3 (9) |
| Możliwość pokazania relacji i ograniczeń | 3 | 3 (9) | 5 (15) |
| Próg wejścia | 2 | 5 (10) | 3 (6) |
| Dostęp bez opłat / bez zależności od konta | 2 | 5 (10) | 4 (8) |
| **Suma ważona** | **10** | **44** | **38** |

**Propozycja:** rozpocząć od Mermaid ER w Markdownie. Jeśli model będzie wymagał szczegółowych ograniczeń lub eksportów do innych narzędzi, ponownie ocenić dbdiagram.io i zachować eksport / źródło w repozytorium.

### 2.4. Makiety UI — Penpot vs Figma

| Kryterium | Waga | Penpot | Figma |
|---|---:|---:|---:|
| Eksport możliwy do dołączenia do repozytorium | 3 | 4 (12) | 4 (12) |
| Współpraca nad makietą | 3 | 4 (12) | 5 (15) |
| Próg wejścia | 2 | 3 (6) | 4 (8) |
| Dostępność planu bez opłat / otwartość | 3 | 5 (15) | 3 (9) |
| **Suma ważona** | **11** | **45** | **44** |

**Propozycja:** Penpot jako rozwiązanie otwarte. Wyniki pracy nad interfejsem należy zachować w repozytorium w formie plików źródłowych oraz eksportów SVG/PNG. Jeśli zespół już biegle zna Figmę, może zaproponować zmianę z uzasadnieniem.

### 2.5. Dokumentacja i repozytorium

| Obszar | Propozycja | Format w repozytorium |
|---|---|---|
| Repozytorium | GitHub | pliki projektu, historia commitów, PR |
| Dokumentacja | Markdown | `.md` |
| Diagram kontekstu | Mermaid | blok kodu w `.md` |
| Diagramy BPMN/UML | diagrams.net | `.drawio` + eksport `.png`/`.svg` |
| Model danych | Mermaid ER na start | `.md`; ewentualny eksport dodatkowo |
| Makiety UI | Penpot | eksport `.svg`/`.png` i link tylko jako uzupełnienie |
| Zadania i pytania | GitHub Issues + Projects | Issues przypisane do osób i widok tablicy |
| Komunikacja | dotychczasowy wspólny komunikator zespołu — do potwierdzenia | istotne ustalenia przenosimy do Issue / ADR |

## 3. Decyzja

Proponujemy powyższy zestaw, ponieważ wyniki pracy pozostają w repozytorium lub mogą być łatwo wyeksportowane, a narzędzia nie wymagają zakupu licencji przez wszystkich członków. To propozycja; każdy członek powinien potwierdzić dostęp do narzędzi i akceptację przed zmianą statusu ADR na „przyjęta”.

## 4. Konsekwencje

**Zyskujemy:** wspólną historię, możliwość recenzowania zmian, prostą kontrolę linków i identyfikatorów, możliwość kontynuacji dokumentacji na kolejnych zajęciach.

**Koszty i ryzyka:** GitHub Projects wymaga krótkiego wdrożenia; diagram tekstowy jest mniej wygodny przy złożonym BPMN; makiety trzeba eksportować, by czytać je bez otwierania narzędzia; wybrane usługi mogą zmienić darmowe plany.

**Działania:** koordynator tworzy projekt i etykiety; każda osoba przyjmuje przynajmniej jedno Issue; zespół potwierdza dostęp i akceptuje albo koryguje ADR; w razie zmiany narzędzia zapisujemy powód w nowej wersji ADR.

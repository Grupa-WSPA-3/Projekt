# Dokumentacja projektu SKW

To miejsce zawiera dokumentację analityczną i materiały projektowe. Zmiany należy wprowadzać w repozytorium; większe aktualizacje powinny być przesyłane przez Pull Request do przeglądu przez innego członka zespołu.

## Dokumenty podstawowe

| Plik | Zawartość |
|---|---|
| [01-karta-projektu.md](01-karta-projektu.md) | problem, cel, interesariusze, użytkownicy, zakres IN/OUT, założenia i wstępne ryzyka |
| [02-slownik.md](02-slownik.md) | pojęcia dziedzinowe, definicje, synonimy, homonimy i źródła |
| [03-wymagania.md](03-wymagania.md) | potrzeby N-xx oraz wstępne wymagania funkcjonalne i niefunkcjonalne |
| [ADR-001](adr/ADR-001-narzedzia.md) | decyzja dotycząca narzędzi pracy projektowej |

## Kontekst i rozmowy

- [Diagram kontekstu](06-architektura/kontekst.md) — system, role zewnętrzne i przepływy informacji.
- [Pytania do klienta](spotkania/pytania-do-klienta.md) — pytania do rozmowy i weryfikacji założeń.
- [Protokół wywiadu](spotkania/wywiad-1.md) — miejsce na ustalenia, cytaty, terminy, sprzeczności i pytania otwarte.
- [Otwarte kwestie](12-otwarte-kwestie.md) — pytania wymagające odpowiedzi lub decyzji.
  
## Struktura pozostałych obszarów

- [04-procesy](04-procesy/) — miejsce na opis rozpoznanych procesów.
- [05-przypadki-uzycia](05-przypadki-uzycia/) — miejsce na przypadki użycia.
- [06-architektura](06-architektura/) — kontekst systemu i granice rozwiązania.
- [07-model-dziedzinowy](07-model-dziedzinowy/) — miejsce na model dziedzinowy.
- [08-baza-danych](08-baza-danych/) — miejsce na projekt bazy danych.
- [09-interfejs](09-interfejs/) — miejsce na projekt interfejsu.
- [10-model-wdrozenia](10-model-wdrozenia/) — miejsce na model wdrożenia.
- [11-plan-testow](11-plan-testow/) — miejsce na plan testów.

Katalogi bez opracowanych artefaktów zawierają wyłącznie plik techniczny `.gitkeep`, aby zachować docelową strukturę repozytorium. Nie oznacza to, że dany obszar jest już opracowany.

## Status i wiarygodność źródeł

Karta projektu i słownik są opracowane w wersji 0.3. Dokument wymagań zawiera 10 potrzeb, 18 wstępnych wymagań funkcjonalnych i 8 wstępnych wymagań niefunkcjonalnych.

Potrzeby i kryteria oparte wyłącznie na założeniach zespołu należy zweryfikować. Protokół wywiadu jest przygotowany jako szablon i wymaga uzupełnienia rzeczywistymi ustaleniami oraz dosłownymi cytatami. Nie dopisujemy fikcyjnych wypowiedzi ani nie oznaczamy niezweryfikowanych założeń jako potwierdzonych.

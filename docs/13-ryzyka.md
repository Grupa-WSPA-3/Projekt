# Rejestr ryzyk projektu SKW

**Wersja:** 0.2 — aktualizacja po opracowaniu procesów P-00…P-03  
**Ocena:** prawdopodobieństwo i wpływ są jakościową oceną zespołu, nie wynikiem pomiaru.

| ID | Ryzyko | Prawdopodobieństwo | Wpływ | Właściciel | Działanie ograniczające | Status |
|---|---|---|---|---|---|---|
| R-01 | Brak rzeczywistego protokołu wywiadu spowoduje, że potrzeby i AS-IS pozostaną hipotezami. | wysokie | wysokie | Maksym Tymoshenko | uzupełnić protokół wyłącznie z faktycznych notatek; oddzielić cytaty od interpretacji; zweryfikować N-xx | otwarte — blokuje zatwierdzenie analizy |
| R-02 | Dwie osoby równocześnie spróbują zająć ostatnie miejsce, co może doprowadzić do przekroczenia limitu. | średnie | wysokie | Kostiantyn Kyrylenko | atomowa transakcja / ograniczenie w bazie; test współbieżności dla FR-08 i BR-02 | aktywne |
| R-03 | Niejasne zasady edycji i anulowania konsultacji spowodują niespójne statusy terminów i zapisów. | wysokie | wysokie | Maksym Tymoshenko | rozstrzygnąć Q-03 i Q-04; przegląd FR-10, FR-12, FR-14 oraz BR-05/BR-06 | otwarte |
| R-04 | Rozszerzanie zakresu o wideokonferencje, SSO, plan zajęć i powiadomienia utrudni ukończenie v1. | średnie | wysokie | cały zespół | utrzymywać OUT; nowe pomysły zapisywać jako przyszłe rozszerzenia, nie dodawać bez decyzji | aktywne |
| R-05 | Lista zapisów ujawni dane studentów osobom bez odpowiednich uprawnień. | średnie | wysokie | Alina Semeniuk | macierz uprawnień, minimalizacja danych, testy negatywne dla FR-02 i FR-13; rozstrzygnąć Q-06 | otwarte |
| R-06 | FR, BR, historyjki, procesy i macierz rozjadą się po zmianie jednego z dokumentów. | średnie | średnie | Sofiia Vetvytska | aktualizować powiązane artefakty w jednym PR; sprawdzać identyfikatory i kolumnę „Proces” | aktywne |
| R-07 | Niejednoznaczne pojęcia „termin”, „zapis”, „wolne miejsce” i „anulowanie” spowodują różne interpretacje. | średnie | średnie | Sofiia Vetvytska | stosować słownik 0.3 jako źródło nazw kanonicznych; dokumentować homonimy i synonimy | aktywne |
| R-08 | Zadania bez właścicieli lub kryteriów akceptacji zostaną pominięte albo wykonane podwójnie. | niskie / średnie | wysokie | Maksym Tymoshenko | każde zadanie jako Issue z jednym właścicielem, etykietą i sprawdzalnym rezultatem | aktywne |
| R-09 | Założone progi wydajności (5 000 terminów, 50 użytkowników, 2 s) okażą się nieadekwatne do docelowej skali. | średnie | średnie | Kostiantyn Kyrylenko | potwierdzić profil obciążenia; nie traktować progów jako faktów o środowisku uczelni | do ponownej oceny |
| R-10 | Brak indywidualnych commitów / recenzji utrudni wykazanie wkładu każdego członka zespołu. | średnie | średnie | cały zespół | każdy członek wykonuje przypisane zadanie, tworzy własny PR / commit i recenzuje pracę innej osoby | aktywne |

## Skala i zasady aktualizacji

- **Prawdopodobieństwo:** niskie / średnie / wysokie.
- **Wpływ:** niski / średni / wysoki.
- Ryzyko o wysokim wpływie należy omówić na spotkaniu zespołu.
- Status „zamknięte” wymaga dowodu: odpowiedzi, decyzji, testu, PR lub innego artefaktu.
- Po zmianie wymagań należy ponownie ocenić ryzyka powiązane z tym wymaganiem.

## Najważniejsze ryzyka przed zatwierdzeniem dokumentacji

1. R-01 — brak zweryfikowanych danych wywiadu: nie wolno prezentować P-00 jako potwierdzonego procesu.
2. R-02 — integralność rezerwacji: musi być rozwiązana na poziomie logiki transakcyjnej, nie tylko widoku UI.
3. R-03 / R-05 — zasady anulowania oraz prywatność list zapisów wymagają decyzji i testów.

# ADR-002: Styl architektury — modularny monolit

**Status:** propozycja do zatwierdzenia przez zespół  
**Data:** 2026-11-23  
**Autorzy:** zespół SKW  
**Zakres:** architektura ogólna v1

## Kontekst

SKW jest systemem webowym: Student przegląda terminy, zapisuje się i anuluje własny zapis; Wykładowca zarządza własnymi terminami i listami zapisów; Administrator zarządza kontami i rolami.

Projekt realizuje jeden zespół czteroosobowy. Nie ma wykazanego zapotrzebowania na niezależne skalowanie obszarów ani osobne wdrożenia wielu zespołów. Reguły limitu miejsc, zapisu i anulowania muszą natomiast zachować spójność transakcyjną. Framework i język implementacji nie są jeszcze zatwierdzone.

## Rozważane opcje

1. **Monolit warstwowy bez jawnych granic domenowych** — jedna aplikacja, ale logika może z czasem stać się silnie powiązana.
2. **Modularny monolit** — jeden backend wdrażany jako całość, z modułami i jawnymi interfejsami; SPA jako klient webowy i relacyjna baza.
3. **Mikroserwisy** — osobno wdrażane usługi dla terminów, zapisów, kont i innych obszarów.

## Decyzja

**Proponowany wybór: modularny monolit w modelu SPA + Backend API + relacyjna baza danych.**

Backend pozostaje jednym wdrażanym artefaktem. W jego wnętrzu wyznacza się moduły:
- Konta i role;
- Terminy konsultacji;
- Dostępność i zapisy;
- Administracja;
- Statusy operacji.

Moduły komunikują się przez jawne operacje / interfejsy backendu. Moduł nie odczytuje ani nie modyfikuje bezpośrednio tabel należących do innego modułu. Wspólna transakcja backendu i bazy obsługuje krytyczną operację zapisu na ostatnie miejsce.

## Dlaczego nie mikroserwisy?

- jeden mały zespół tworzy i opisuje system;
- brak wymagań na niezależne skalowanie terminów, zapisów i administracji;
- brak odrębnych zespołów utrzymujących osobne usługi;
- mikroserwisy wprowadziłyby dodatkowe wdrożenia, komunikację sieciową, monitoring i trudniejszą spójność danych;
- granice dziedziny są nadal weryfikowane, więc przedwczesne rozdzielenie byłoby kosztowne.

Modularny monolit pozwala zachować granice modułów i w razie rzeczywistej potrzeby wydzielić moduł w późniejszym etapie.

## Konsekwencje

### Korzyści
- jedno wdrożenie i prostszy model operacyjny;
- łatwiejsza kontrola spójności zapisu i limitu miejsc w jednej transakcji;
- granice odpowiedzialności można testować i przeglądać w PR;
- mniejsza liczba elementów infrastruktury.

### Koszty i ryzyka
- moduły nie skalują się niezależnie;
- konieczna jest dyscyplina, aby nie tworzyć zależności przez bezpośredni dostęp do cudzych tabel;
- awaria backendu wpływa na cały system;
- monitoring, kopie zapasowe i środowisko wdrożenia wymagają dalszego projektu.

## Co pozostaje otwarte

- wybór języka i frameworka backendu;
- wybór frameworka SPA;
- potwierdzenie relacyjnego silnika i środowiska wdrożenia;
- szczegóły uwierzytelniania oraz zakładania kont (Q-05);
- ewentualne integracje SSO / planu zajęć — poza v1, Q-12.

## Powiązania

- C4 L1: [kontekst.md](../06-architektura/kontekst.md)
- C4 L2: [kontenery.md](../06-architektura/kontenery.md)
- Wpływ NFR: [kontenery.md](../06-architektura/kontenery.md#wpływ-nfr-na-architekturę)
- Make-or-buy: [make-or-buy.md](../06-architektura/make-or-buy.md)

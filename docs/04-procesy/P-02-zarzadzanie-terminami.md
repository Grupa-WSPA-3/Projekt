# P-02 — Zarządzanie terminami przez wykładowcę (TO-BE)

**Wersja:** 0.1 · **Właściciel:** @miumeowww · **Issue:** [#6](https://github.com/Grupa-WSPA-3/Projekt/issues/6) · **Powiązane:** FR-02, FR-11…FR-15, FR-16, BR-01, BR-04…BR-06, BR-08, BR-09

## Cel procesu
Umożliwić wykładowcy zarządzanie własnymi terminami konsultacji oraz kontrolę listy zapisanych studentów zgodnie z rolą i regułami systemu.

## Wyzwalacz
Wykładowca chce utworzyć, zmienić, sprawdzić lub anulować termin konsultacji.

## Uczestnicy (tory)
- **Wykładowca** — inicjuje czynności na własnych terminach.
- **System SKW** — weryfikuje rolę i właściciela terminu, sprawdza reguły, zapisuje zmiany oraz prezentuje status.

## Wyniki
- termin utworzony lub poprawnie zmieniony;
- lista zapisów wyświetlona uprawnionemu wykładowcy;
- termin anulowany, a powiązane zapisy otrzymują czytelny status;
- operacja odrzucona z powodu danych, uprawnień lub aktywnych zapisów.

## Diagram BPMN 2.0

![P-02 — zarządzanie terminami przez wykładowcę](P-02-zarzadzanie-terminami.svg)

Źródło: [P-02-zarzadzanie-terminami.bpmn](P-02-zarzadzanie-terminami.bpmn).

## Kroki

| Krok | Tor | Typ zadania | Opis | Wymagania |
|---|---|---|---|---|
| P-02.1 | Wykładowca | użytkownika | Zaloguj się do SKW | FR-01, FR-02, BR-09 |
| P-02.2 | Wykładowca | użytkownika | Wybierz czynność: utworzenie, edycja, lista zapisów lub anulowanie | FR-11…FR-14 |
| P-02.3 | Wykładowca | użytkownika | Wprowadź dane nowego terminu albo wybierz własny termin | FR-11, FR-12, FR-13, FR-14 |
| P-02.4 | System SKW | usługi | Sprawdź rolę, właściciela terminu i poprawność zakresu dat | FR-02, BR-01, BR-04 |
| P-02.5 | System SKW | usługi | Sprawdź, czy edytowany termin ma aktywne zapisy | FR-12, BR-05 |
| P-02.6 | System SKW | usługi | Zapisz nowy termin lub dozwoloną zmianę | FR-11, FR-12 |
| P-02.7 | Wykładowca / System SKW | użytkownika / usługi | Wyświetl listę studentów zapisanych na własny termin | FR-13, BR-08 |
| P-02.8 | Wykładowca | użytkownika | Potwierdź anulowanie własnego terminu | FR-14, BR-04 |
| P-02.9 | System SKW | usługi | Oznacz termin jako anulowany i zaktualizuj status powiązanych aktywnych zapisów | FR-14, FR-16, BR-06 |
| P-02.10 | System SKW | usługi | Pokaż wykładowcy i studentom aktualne statusy | FR-16 |

## Wyjątki i ścieżki alternatywne

| Wyjątek | Gdzie | Reakcja | Wymaganie / BR |
|---|---|---|---|
| Użytkownik nie ma roli Wykładowca | P-02.1 / P-02.4 | Odmów dostępu do zarządzania terminami | FR-02, BR-04, BR-09 |
| Wykładowca próbuje zmienić termin innej osoby | P-02.3–P-02.4 | Odrzuć operację bez zmiany danych | FR-02, BR-04 |
| Początek terminu jest w przeszłości lub koniec nie jest późniejszy niż początek | P-02.4 | Odrzuć dane i pokaż przyczynę | BR-01, FR-11, FR-12 |
| Edytowany termin ma aktywne zapisy | P-02.5 | Zablokuj edycję; wykładowca może rozważyć anulowanie terminu i utworzenie nowego | FR-12, BR-05 |
| Anulowany termin ma aktywne zapisy | P-02.9 | Oznacz powiązane zapisy jako anulowane z powodu anulowania terminu i pokaż status | FR-14, FR-16, BR-06 |

## Doprecyzowania z walkthrough

- Odmowa edycji terminu z aktywnymi zapisami powinna zwracać użytkownikowi zrozumiałą przyczynę, a dane terminu pozostają niezmienione (FR-12, BR-05).
- Anulowanie terminu przez wykładowcę musi być odróżnione od anulowania pojedynczego zapisu przez studenta; statusy powiązanych zapisów mają jasno wskazywać przyczynę zmiany (FR-14, FR-16, BR-06).

Są to doprecyzowania wynikające ze spójności procesów i istniejących wymagań; nie stanowią potwierdzenia reguł przez klienta.

## Otwarte pytania
- Czy termin z aktywnymi zapisami może być wyjątkowo edytowany zamiast anulowania? ([Q-04](https://github.com/Grupa-WSPA-3/Projekt/issues/16))
- Czy administrator może przeglądać listy zapisów? ([Q-06](https://github.com/Grupa-WSPA-3/Projekt/issues/17))
- Jak długo przechowywać anulowane terminy i zapisy? ([Q-11](https://github.com/Grupa-WSPA-3/Projekt/issues/20))

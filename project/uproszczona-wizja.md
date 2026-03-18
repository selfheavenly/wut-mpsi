# Uproszczona wizja systemu

# System zarządzania wypożyczeniami sprzętu IT — Stack Underflow sp. z o.o.

---

## Udziałowcy

- Dyrektor techniczny
- Lider zespołu Helpdesk
- Analityk biznesowy

## Problemy

- Duży nakład pracy manualnej
- Długi czas realizacji zadań
- Utrudnione monitorowanie statusu
- Utrudniony dostęp do informacji
- Rozbieżności w aktywach (ewidencja vs rzeczywistość)

## Potrzeby udziałowców

- Centralizacja i uporządkowanie danych o sprzęcie
- Usprawnienie i zwiększenie przejrzystości procesów
- Automatyzacja przypisywania i rozliczania sprzętu
- Generowanie raportów stanu majątku IT

## Użytkownicy

- Pracownik (użytkownik końcowy)
- Przełożony pracownika (użytkownik końcowy)
- Specjalista Helpdesk (użytkownik końcowy)

## Aktorzy

- A-01 Pracownik (użytkownik końcowy)
- A-02 Przełożony pracownika (użytkownik końcowy)
- A-03 Specjalista Helpdesk (użytkownik końcowy)
- A-04 Active Directory (aktor zewnętrzny)
- A-05 System (aktor wewnętrzny — automatyczny)

---

## Procesy

### P1 — Obsługa wniosku o wypożyczenie sprzętu

> Cel: sformalizowanie żądania pracownika z dwuetapową autoryzacją i automatycznym przypisaniem zasobu

- Wyzwalacz: pracownik zgłasza potrzebę pozyskania sprzętu
- Wynik: sprzęt wydany i przypisany do profilu pracownika, lub wniosek odrzucony z powiadomieniem
- Aktorzy: A-01, A-02, A-03, A-04, A-05

### P2 — Zwrot sprzętu

> Cel: zamknięcie cyklu wypożyczenia z weryfikacją stanu i archiwizacją protokołu

- Wyzwalacz: pracownik inicjuje zwrot lub mija termin zwrotu
- Wynik: sprzęt odpisany z profilu, status zaktualizowany, protokół PDF wygenerowany
- Aktorzy: A-01, A-03, A-05

### P3 — Zarządzanie cyklem życia urządzenia

> Cel: utrzymanie aktualnego inwentarza od zakupu do utylizacji z pełną historią zdarzeń

- Wyzwalacz: zakup nowego sprzętu lub zmiana stanu urządzenia
- Wynik: dane urządzenia aktualne i spójne, historia zdarzeń zachowana
- Aktorzy: A-03, A-05

### P4 — Offboarding pracownika

> Cel: kompleksowe rozliczenie całości sprzętu przy zakończeniu zatrudnienia

- Wyzwalacz: HR wprowadza datę zakończenia zatrudnienia pracownika
- Wynik: cały sprzęt zwrócony i odpisany, protokół offboardingu wygenerowany, konto dezaktywowane w AD
- Aktorzy: A-01, A-03, A-04, A-05

---

## Przypadki użycia

### P1 — Obsługa wniosku o wypożyczenie

- UC-01 Złożenie wniosku o wypożyczenie _(A-01, A-04)_
- UC-02 Zatwierdzenie wniosku przez przełożonego _(A-02)_ — «extend» UC-01
- UC-03 Akceptacja wniosku przez Helpdesk _(A-03)_ — «extend» UC-02
- UC-04 Automatyczne przypisanie sprzętu _(A-05)_ — «include» UC-03
- UC-05 Odrzucenie wniosku _(A-02 lub A-03)_ — «extend» UC-02/03

### P2 — Zwrot sprzętu

- UC-06 Inicjacja zwrotu przez pracownika _(A-01)_
- UC-07 Rejestracja zwrotu przez Helpdesk _(A-03, A-05)_ — «include» UC-06
- UC-08 Obsługa zwrotu przeterminowanego _(A-03, A-05)_ — «extend» UC-07
- UC-09 Obsługa sprzętu uszkodzonego _(A-03)_ — «extend» UC-07

### P3 — Zarządzanie cyklem życia urządzenia

- UC-10 Dodanie urządzenia do inwentarza _(A-03)_
- UC-11 Edycja danych urządzenia _(A-03)_ — «extend» UC-10
- UC-12 Zmiana statusu urządzenia _(A-03, A-05)_ — «include» UC-10
- UC-13 Kategoryzacja urządzenia _(A-03)_ — «include» UC-10

### P4 — Offboarding pracownika

- UC-14 Inicjacja procesu offboardingu _(A-05)_
- UC-15 Przegląd i obsługa listy zwrotów _(A-03)_ — «include» UC-14
- UC-16 Zwrot sprzętu w ramach offboardingu _(A-01, A-03)_ — «include» UC-15 → wywołuje P2/UC-06
- UC-17 Generowanie protokołu offboardingu _(A-05)_ — «include» UC-15
- UC-18 Deaktywacja konta w AD _(A-04, A-05)_ — «include» UC-14

---

## Wymagania

### Funkcjonalne (F)

#### P1 — Obsługa wniosku

- F-P1-01 Formularz wniosku z wyborem kategorii, uzasadnieniem i typem czasu (określony/nieokreślony)
- F-P1-02 Automatyczna identyfikacja przełożonego z AD (pole tylko do odczytu)
- F-P1-03 Powiadomienia e-mail na każdym etapie autoryzacji
- F-P1-04 Wybór konkretnego urządzenia przez Helpdesk (kod inwentarzowy lub skan QR)
- F-P1-05 Automatyczna zmiana statusu na _w_użyciu_ i generowanie protokołu PDF po akceptacji

#### P2 — Zwrot sprzętu

- F-P2-01 Inicjacja zwrotu z poziomu panelu użytkownika (lista aktywnych wypożyczeń)
- F-P2-02 Wybór nowego statusu urządzenia przez Helpdesk: _nowy_ lub _w_naprawie_
- F-P2-03 Automatyczne generowanie protokołu zdawczo-odbiorczego (PDF)
- F-P2-04 Alert dla Helpdesku przy wykryciu zwrotu przeterminowanego

#### P3 — Cykl życia urządzenia

- F-P3-01 Automatyczne generowanie kodu inwentarzowego PREFIX-NNNN (LAP, MON, DOK, TEL, PER, INN)
- F-P3-02 Macierz dozwolonych przejść statusów: _nowy → w_użyciu → w_naprawie → nowy / zutylizowany_
- F-P3-03 Historia zdarzeń urządzenia: każda zmiana statusu, kategorii i przypisania (kto, co, kiedy)

#### P4 — Offboarding

- F-P4-01 Automatyczna generacja listy aktywnych wypożyczeń pracownika w ≤2s od daty zakończenia
- F-P4-02 Natychmiastowe zablokowanie możliwości składania nowych wniosków przez pracownika
- F-P4-03 Panel offboardingu z listą i statusami: _oczekuje / zwrócono / brakujące_
- F-P4-04 Automatyczny zbiorczy protokół PDF po zwrocie ostatniego urządzenia
- F-P4-05 Sygnał deaktywacji konta do Active Directory po zakończeniu offboardingu

### Niefunkcjonalne (NFR)

#### Wydajność

- Z15-W01 Czas odpowiedzi systemu ≤2s (p95) dla wszystkich akcji użytkownika
- Z15-W02 Obsługa min. 200 równoległych sesji bez degradacji

#### Dostępność

- Z15-D01 SLA ≥99,5%
- Z15-D02 Interfejs responsywny (RWD), dostępny z dowolnej przeglądarki

#### Bezpieczeństwo

- Z15-B01 Kontrola dostępu oparta na rolach (RBAC): pracownik / przełożony / helpdesk
- Z15-B02 Logowanie wyłącznie przez SSO z Active Directory
- Z15-B03 Szyfrowanie połączeń TLS ≥1.2
- Z15-B04 Audit log każdej operacji na danych

#### Skalowalność

- Z15-S01 Do 2 000 użytkowników i 10 000 urządzeń
- Z15-S02 Integracja z AD obsługuje do 50 działów

#### Zgodność

- Z15-C01 Zgodność z RODO; dane zachowane min. 5 lat po offboardingu
- Z15-C02 Interfejs w języku polskim

---

## Ograniczenia

- OGR-01 Uwierzytelnianie wyłącznie przez SSO / Active Directory — brak lokalnych haseł
- OGR-02 Kod inwentarzowy globalnie unikalny — duplikaty blokowane na poziomie bazy danych
- OGR-03 Zmiana statusu urządzenia ograniczona macierzą dozwolonych przejść stanów
- OGR-04 Protokoły wydania i zwrotu niemodyfikowalne po wygenerowaniu (archiwum PDF)
- OGR-05 Wniosek może złożyć wyłącznie pracownik z identyfikowalnym przełożonym w AD
- OGR-06 Panel offboardingu dostępny wyłącznie dla roli Helpdesk

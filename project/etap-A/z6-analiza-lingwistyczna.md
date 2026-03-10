# Analiza lingwistyczna

**Projekt:** System do zarządzania wypożyczeniami sprzętu

**Firma:** Stack Underflow sp. z o.o.

**Skład zespołu:**

- Wiktor Konieczny (348380),
- Kamil Sobierajski (348417),
- Kamil Urbaś (348392)

---

## 1. Grupy rzeczownikowe (wyróżnione w tekście)

| Lp. | Grupa rzeczownikowa         |
| --- | --------------------------- |
| 1   | zarząd korporacji           |
| 2   | Stack Underflow             |
| 3   | realizacja systemu          |
| 4   | aplikacja webowa            |
| 5   | sprzęt elektroniczny        |
| 6   | pracownicy                  |
| 7   | firma                       |
| 8   | software house              |
| 9   | start-up                    |
| 10  | kadra pracownicza           |
| 11  | model hybrydowy             |
| 12  | struktura pracy             |
| 13  | dział wsparcia technicznego |
| 14  | Helpdesk                    |
| 15  | flota sprzętu IT            |
| 16  | laptopy                     |
| 17  | monitory                    |
| 18  | stacje dokujące             |
| 19  | telefony                    |
| 20  | urządzenia peryferyjne      |
| 21  | myszki                      |
| 22  | klawiatury                  |
| 23  | ładowarki                   |
| 24  | komunikacja mailowa         |
| 25  | pliki Excel                 |
| 26  | protokół wydawania sprzętu  |
| 27  | protokół zdawczo-odbiorczy  |
| 28  | wypożyczenie                |
| 29  | wniosek                     |
| 30  | pracownik Helpdesku         |
| 31  | kierownik                   |
| 32  | menedżer                    |
| 33  | kod inwentarzowy            |
| 34  | kod QR                      |
| 35  | kategoria                   |
| 36  | status urządzenia           |
| 37  | profil pracownika           |
| 38  | Active Directory            |
| 39  | panel użytkownika           |
| 40  | raport                      |
| 41  | statystyki awaryjności      |
| 42  | termin zwrotu               |
| 43  | offboarding                 |
| 44  | ścieżka autoryzacji         |
| 45  | dokument                    |
| 46  | zasób                       |
| 47  | byt                         |
| 48  | cykl życia urządzenia       |

---

## 2. Grupy czasownikowe (wyróżnione w tekście)

| Lp. | Grupa czasownikowa                                |
| --- | ------------------------------------------------- |
| 1   | zlecił realizację systemu                         |
| 2   | zarządzać sprzętem elektronicznym                 |
| 3   | powiększenie kadry pracowniczej                   |
| 4   | wykonywać obowiązki (model hybrydowy)             |
| 5   | zarządzać flotą sprzętu IT                        |
| 6   | opierały się (tradycyjne metody)                  |
| 7   | przestał być wydajny                              |
| 8   | trwa zbyt długo                                   |
| 9   | wydawanie / wymiana sprzętu                       |
| 10  | ciąży (nakład pracy)                              |
| 11  | złożyć wniosek                                    |
| 12  | pobierać sprzęt testowy                           |
| 13  | zapominają o terminowym zwrocie                   |
| 14  | pozwoli na rozliczenie                            |
| 15  | musi być traktowane                               |
| 16  | przypisane będą wnioski                           |
| 17  | złożenie wniosku musi wymagać ścieżki autoryzacji |
| 18  | przekazuje wniosek do menedżera                   |
| 19  | wydać sprzęt (Helpdesk)                           |
| 20  | automatyczne przypisanie sprzętu                  |
| 21  | generować raporty                                 |
| 22  | generować zestawienia przeterminowanych           |
| 23  | generować statystyki awaryjności                  |
| 24  | wygenerować listę sprzętu do zwrotu (offboarding) |
| 25  | zidentyfikować użytkownika (Active Directory)     |
| 26  | skanować kod QR                                   |
| 27  | kategoryzować sprzęt                              |
| 28  | zmienić status urządzenia                         |

---

## 3. Specyfikacja grup czasownikowych

| Lp. | Grupy czasownikowe                                 | Usługa (przypadek użycia)     | Operacja lub odpowiedzialność |
| --- | -------------------------------------------------- | ----------------------------- | ----------------------------- |
| 1   | zlecił realizację systemu                          |                               | ZlecenieRealizacji            |
| 2   | zarządzać sprzętem elektronicznym                  | ZarządzanieSprzętem           |                               |
| 3   | dodać / edytować urządzenie                        | DodawanieUrządzenia           |                               |
| 4   | kategoryzować sprzęt                               |                               | KategoryzacjaSprzętu          |
| 5   | zarządzać statusem urządzenia                      |                               | ZmianaStatusuUrządzenia       |
| 6   | zidentyfikować użytkownika (AD)                    |                               | IdentyfikacjaUżytkownika      |
| 7   | wyświetlić panel użytkownika                       | WyświetleniePaneluUżytkownika |                               |
| 8   | złożyć wniosek o wypożyczenie                      | ZłożenieWniosku               |                               |
| 9   | zatwierdzić wniosek (kierownik)                    | ZatwierdzanieWniosku          |                               |
| 10  | zaakceptować / odrzucić wniosek (Helpdesk)         | AkceptacjaWniosku             |                               |
| 11  | przypisać sprzęt do pracownika                     |                               | PrzypisanieSprzętu            |
| 12  | zwrócić sprzęt                                     | ZwrotSprzętu                  |                               |
| 13  | generować raporty stanu majątku IT                 | GenerowanieRaportu            |                               |
| 14  | generować zestawienie przeterminowanych wypożyczeń | ZestawienieTerminówZwrotu     |                               |
| 15  | generować statystyki awaryjności                   | StatystykiAwaryjności         |                               |
| 16  | przeprowadzić szybkie rozliczenie (offboarding)    | SzybkieRozliczenieOffboarding |                               |
| 17  | skanować kod QR                                    |                               | SkanowanieKoduQR              |
| 18  | powiadomić / przesłać wniosek                      |                               | PowiadomieniePrzekierowanie   |
| 19  | integrować z Active Directory                      |                               | IntegracjaAD                  |

---

## 4. Specyfikacja grup rzeczownikowych

| Lp. | Grupy rzeczownikowe       | Kandydat na obiekt (klasę) | Kandydat na atrybut    |
| --- | ------------------------- | -------------------------- | ---------------------- |
| 1   | zarząd korporacji         |                            |                        |
| 2   | aplikacja webowa          | AplikacjaWebowa            |                        |
| 3   | sprzęt / urządzenie IT    | Urządzenie                 |                        |
| 4   | laptop                    |                            | → kategoria Urządzenia |
| 5   | monitor                   |                            | → kategoria Urządzenia |
| 6   | stacja dokująca           |                            | → kategoria Urządzenia |
| 7   | telefon                   |                            | → kategoria Urządzenia |
| 8   | urządzenia peryferyjne    |                            | → kategoria Urządzenia |
| 9   | kod inwentarzowy / kod QR |                            | → atrybut Urządzenia   |
| 10  | kategoria urządzenia      |                            | → atrybut Urządzenia   |
| 11  | status urządzenia         |                            | → atrybut Urządzenia   |
| 12  | cykl życia urządzenia     | CyklŻyciaUrządzenia        |                        |
| 13  | pracownik                 | Pracownik                  |                        |
| 14  | kierownik / menedżer      | Kierownik                  |                        |
| 15  | pracownik Helpdesku       | PracownikHelpdesk          |                        |
| 16  | profil pracownika         | ProfilPracownika           |                        |
| 17  | wniosek o wypożyczenie    | Wniosek                    |                        |
| 18  | ścieżka autoryzacji       | ŚcieżkaAutoryzacji         |                        |
| 19  | wypożyczenie              | Wypożyczenie               |                        |
| 20  | termin zwrotu             |                            | → atrybut Wypożyczenia |
| 21  | dokument (protokół)       | Dokument                   |                        |
| 22  | raport                    | Raport                     |                        |
| 23  | statystyki awaryjności    | StatystykaAwaryjności      |                        |
| 24  | panel użytkownika         | PanelUżytkownika           |                        |
| 25  | Active Directory          | ActiveDirectory            |                        |
| 26  | Helpdesk (dział)          |                            |                        |
| 27  | offboarding               | ProcesOffboardingu         |                        |

---

## 5. Wyznaczone elementy projektowe

### 5.1. Aktorzy systemu

| Lp. | Aktor                                |
| --- | ------------------------------------ |
| 1   | Pracownik                            |
| 2   | Kierownik / Menedżer                 |
| 3   | Pracownik Helpdesku                  |
| 4   | System Active Directory (zewnętrzny) |

### 5.2. Klasy systemu

| Lp. | Klasa                 |
| --- | --------------------- |
| 1   | Urządzenie            |
| 2   | Wypożyczenie          |
| 3   | Wniosek               |
| 4   | ŚcieżkaAutoryzacji    |
| 5   | Dokument              |
| 6   | Raport                |
| 7   | PanelUżytkownika      |
| 8   | StatystykaAwaryjności |
| 9   | ProcesOffboardingu    |

### 5.3. Wybrane atrybuty klas

| Lp. | Atrybut (klasa: atrybuty)                                                                               |
| --- | ------------------------------------------------------------------------------------------------------- |
| 1   | Urządzenie: kodInwentarzowy, kategoria, status (nowy / w użyciu / w naprawie / zutylizowany), cyklŻycia |
| 2   | Pracownik: id (AD), imię, nazwisko, stanowisko, aktualnySprzęt, wnioski, dokumenty                      |
| 3   | Wypożyczenie: dataPoczątku, dataKońca (opcjonalnie), terminZwrotu, status                               |
| 4   | Wniosek: dataSłożenia, typSprzętu, czasOkreślony, statusAutoryzacji                                     |

### 5.4. Usługi systemu (przypadki użycia)

| Lp. | Usługa / Przypadek użycia                                |
| --- | -------------------------------------------------------- |
| 1   | Zarządzanie urządzeniami (dodaj / edytuj / zmień status) |
| 2   | Złożenie wniosku o wypożyczenie                          |
| 3   | Zatwierdzenie wniosku przez kierownika                   |
| 4   | Akceptacja / odrzucenie wniosku przez Helpdesk           |
| 5   | Zwrot sprzętu                                            |
| 6   | Wyświetlenie panelu użytkownika                          |
| 7   | Generowanie raportu stanu IT                             |
| 8   | Zestawienie przeterminowanych wypożyczeń                 |
| 9   | Generowanie statystyk awaryjności                        |
| 10  | Szybkie rozliczenie offboardingu                         |

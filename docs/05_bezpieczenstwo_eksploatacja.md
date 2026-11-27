# 5. Bezpieczeństwo, Infrastruktura i Eksploatacja

<!--
Właściciel wiodący: Projektant Danych i Bezpieczeństwa. Termin: v0.9.
Minimum: model uwierzytelniania; macierz RBAC (role z 2.1 × operacje/zasoby z API); analiza danych osobowych (RODO);
parametry infrastruktury; RTO/RPO i polityka kopii zapasowych.
Typowe błędy: role inne niż aktorzy z rozdz. 2.1; "dane są bezpieczne" bez mechanizmu; brak podstawy prawnej i okresu
retencji dla danych osobowych; RTO/RPO niezgodne z NFR dostępności; backup bez testu odtworzenia.
-->

## 5.1. Model uwierzytelniania i autoryzacji

**Uwierzytelnianie:** [np. login + hasło z MFA dla ról personelu; dla użytkowników wewnętrznych — SSO (OpenID Connect) z firmowym dostawcą tożsamości]

**Mechanizm sesji / tokenów:** [np. access token JWT ważny 15 min + refresh token 7 dni w ciasteczku HttpOnly, Secure, SameSite=Strict; unieważnienie przy wylogowaniu]

**Polityka haseł i kont:** [np. min. 12 znaków, sprawdzanie na liście haseł wyciekłych, blokada po 5 nieudanych próbach na 15 min]

### Macierz uprawnień (RBAC)

| Zasób / operacja | ACT-01 Gość | ACT-02 Klient | ACT-03 Pracownik | ACT-04 Administrator |
|---|:-:|:-:|:-:|:-:|
| Przeglądanie terminów (API-01) | ✔ | ✔ | ✔ | ✔ |
| Utworzenie rezerwacji (API-02) | — | ✔ | ✔ | — |
| Podgląd rezerwacji (API-03) | — | własne | ✔ | ✔ |
| Zmiana statusu rezerwacji (API-04) | — | anulowanie własnych | ✔ | ✔ |
| Zarządzanie kontami i rolami | — | — | — | ✔ |
| [ ] | | | | |

## 5.2. Ochrona danych osobowych i zgodność z regulacjami (RODO)

| Kategoria danych | Przykłady pól | Cel przetwarzania | Podstawa prawna (art. 6 RODO) | Okres przechowywania | Kto ma dostęp |
|---|---|---|---|---|---|
| Dane identyfikacyjne klienta | imię, nazwisko, e-mail, telefon | realizacja rezerwacji | art. 6 ust. 1 lit. b (umowa) | [np. 3 lata od ostatniej aktywności] | Pracownik, Administrator |
| Dane rozliczeniowe | [ ] | [ ] | [art. 6 ust. 1 lit. c (obowiązek prawny)] | [np. 5 lat — przepisy podatkowe] | [ ] |
| Logi audytowe | identyfikator użytkownika, IP, czas | bezpieczeństwo | [art. 6 ust. 1 lit. f (uzasadniony interes)] | [ ] | Administrator |

**Realizacja praw osób, których dane dotyczą:** [dostęp, sprostowanie, usunięcie / anonimizacja, przenoszenie — jak system je obsługuje]
**Środki techniczne:** [szyfrowanie w spoczynku i w transmisji, pseudonimizacja, minimalizacja danych, rejestr dostępu]
**Dane szczególnych kategorii (art. 9) / dane dzieci:** [czy występują; jeśli tak — dodatkowe zabezpieczenia]

## 5.3. Wymagania infrastrukturalne i środowiskowe

| Środowisko | Przeznaczenie | Parametry (rekomendowane) | Uwagi |
|---|---|---|---|
| Produkcyjne | [ ] | [np. 2 × vCPU 4, RAM 8 GB dla API; zarządzana baza PostgreSQL 2 vCPU / 4 GB / 100 GB SSD] | [region UE] |
| Testowe (staging) | [ ] | [ ] | [dane fikcyjne / zanonimizowane] |
| Deweloperskie | [ ] | [np. Docker Compose na stacji roboczej] | |

**Sieć i bezpieczeństwo brzegowe:** [np. TLS 1.2+, reverse proxy / WAF, baza niedostępna z Internetu]
**Monitoring i logowanie:** [co monitorujemy, progi alarmowe — powiązanie z NFR-03]
**Gotowość na automatyzację (CI/CD w cz. 2):** [np. aplikacja konfigurowana zmiennymi środowiskowymi, konteneryzacja]

## 5.4. Polityka backupu i scenariusze awaryjne (Disaster Recovery)

| Parametr | Wartość | Uzasadnienie |
|---|---|---|
| **RPO** (maks. akceptowalna utrata danych) | [np. 15 min] | [np. utrata rezerwacji z dłuższego okresu jest nieakceptowalna dla klienta] |
| **RTO** (maks. czas przywrócenia działania) | [np. 4 h] | [spójne z NFR-03] |
| Kopia pełna | [np. codziennie 2:00, retencja 30 dni] | |
| Kopia przyrostowa / WAL | [np. ciągła archiwizacja co 15 min] | |
| Lokalizacja kopii | [np. inny region UE, szyfrowane] | |
| Test odtworzenia | [np. raz na kwartał, raport] | |

### Scenariusze awaryjne

| ID | Scenariusz | Wykrycie | Reakcja | Czas przywrócenia |
|---|---|---|---|---|
| DR-01 | Awaria serwera aplikacji | [monitoring] | [ ] | [ ] |
| DR-02 | Utrata / uszkodzenie bazy danych | [ ] | [odtworzenie z kopii + WAL] | [≤ RTO] |
| DR-03 | Niedostępność systemu zewnętrznego (np. e-mail, płatności) | [ ] | [kolejkowanie, ponowienia] | [ ] |

# 1. Karta Projektu i Uzasadnienie Biznesowe

<!--
Właściciel wiodący: Project Manager. Termin: v0.5 (48 h przed Zjazdem 2).
Minimum: 4–6 modułów In-Scope; ≥ 3 pozycje Out-of-Scope; interesariusze: sponsor, użytkownicy końcowi,
administrator + ≥ 1 zewnętrzny; RACI dla wszystkich rozdziałów × wszystkich członków, dokładnie jedno "A" w wierszu.
Typowe błędy: cel = opis funkcji ("system pozwala…") zamiast korzyści biznesowej; brak mierników sukcesu;
Out-of-Scope pusty lub banalny; RACI z kilkoma "A" w wierszu.
-->

## 1.1. Cel wdrożenia i korzyści biznesowe klienta

**Klient / odbiorca:** [organizacja, dział, osoba decyzyjna]

**Problem (stan obecny):** [3–5 zdań: jak proces przebiega dziś, co idzie źle, jakie są skutki — czas, koszty, błędy, niezadowolenie]

**Cel biznesowy:** [2–3 zdania: jaka zmiana u klienta ma nastąpić dzięki systemowi]

**Mierniki sukcesu:**

| ID | Miernik | Wartość obecna | Wartość docelowa | Sposób pomiaru |
|---|---|---|---|---|
| CEL-01 | [np. średni czas obsługi zgłoszenia] | [np. 3 dni] | [np. ≤ 1 dzień] | [np. raport z systemu, po 3 miesiącach] |
| CEL-02 | [ ] | [ ] | [ ] | [ ] |
| CEL-03 | [ ] | [ ] | [ ] | [ ] |

<!-- Wartości mogą być założeniami zespołu — wtedy oznacz je "(założenie)". -->

## 1.2. Identyfikacja interesariuszy

| ID | Interesariusz | Typ (wewn./zewn.) | Rola wobec systemu | Potrzeby / oczekiwania | Wpływ (N/Ś/W) | Zainteresowanie (N/Ś/W) |
|---|---|---|---|---|---|---|
| INT-01 | [Sponsor — np. dyrektor ds. operacyjnych] | wewn. | finansuje, akceptuje odbiór | [ ] | W | Ś |
| INT-02 | [Użytkownik końcowy — np. klient] | zewn. | korzysta z systemu | [ ] | Ś | W |
| INT-03 | [Pracownik obsługi] | wewn. | korzysta z systemu | [ ] | Ś | W |
| INT-04 | [Administrator systemu] | wewn. | utrzymuje, nadaje uprawnienia | [ ] | Ś | Ś |
| INT-05 | [Interesariusz zewnętrzny — np. dostawca usługi płatności, urząd, IOD] | zewn. | [ ] | [ ] | [ ] | [ ] |

## 1.3. Zakres systemu

### In-Scope (co wchodzi w skład realizowanego projektu)

| ID | Moduł / obszar | Opis (1–2 zdania) |
|---|---|---|
| MOD-01 | [ ] | [ ] |
| MOD-02 | [ ] | [ ] |
| MOD-03 | [ ] | [ ] |
| MOD-04 | [ ] | [ ] |

### Out-of-Scope (funkcjonalności świadomie wyłączone z realizacji)

| ID | Wyłączenie | Uzasadnienie |
|---|---|---|
| OUT-01 | [np. dedykowana aplikacja mobilna] | [np. wersja webowa responsywna wystarcza w v1.0] |
| OUT-02 | [ ] | [ ] |
| OUT-03 | [ ] | [ ] |

### Założenia i ograniczenia

| ID | Rodzaj | Treść | Status |
|---|---|---|---|
| ZAL-01 | założenie | [np. użytkownicy wewnętrzni logują się kontem firmowym (SSO)] | do potwierdzenia z Zamawiającym |
| OGR-01 | ograniczenie | [np. dane przechowywane wyłącznie na terenie UE] | potwierdzone |

### Ryzyka projektowe

| ID | Ryzyko | Prawdopodobieństwo (N/Ś/W) | Wpływ (N/Ś/W) | Reakcja | Właściciel |
|---|---|---|---|---|---|
| R-01 | [ ] | [ ] | [ ] | [ ] | [ ] |
| R-02 | [ ] | [ ] | [ ] | [ ] | [ ] |
| R-03 | [ ] | [ ] | [ ] | [ ] | [ ] |

## 1.4. Skład zespołu projektowego i macierz odpowiedzialności (RACI)

| Imię i nazwisko | Rola wiodąca | Login GitHub | Zastępstwo |
|---|---|---|---|
| [ ] | Project Manager | @[ ] | [ ] |
| [ ] | Analityk Biznesowy | @[ ] | [ ] |
| [ ] | Architekt Systemu | @[ ] | [ ] |
| [ ] | Projektant Danych i Bezpieczeństwa | @[ ] | [ ] |
| [ ] | QA / Tech Writer | @[ ] | [ ] |

**Macierz RACI** — R: wykonuje · A: odpowiada (dokładnie jedno w wierszu) · C: konsultowany · I: informowany

| Zadanie / produkt | [Osoba 1] | [Osoba 2] | [Osoba 3] | [Osoba 4] | [Osoba 5] |
|---|:-:|:-:|:-:|:-:|:-:|
| Rozdz. 1 — Karta projektu | A/R | C | I | I | C |
| Rozdz. 2 — Wymagania (FR) | C | A/R | C | I | R |
| Rozdz. 2 — Wymagania (NFR) | I | R | C | C | A |
| Rozdz. 2 — Diagramy procesów | I | A/R | C | I | C |
| Rozdz. 3 — Architektura i ADR | I | C | A/R | C | C |
| Rozdz. 4 — ERD i słownik danych | I | C | C | A/R | I |
| Rozdz. 4 — Sekwencje i API | I | C | A/R | R | C |
| Rozdz. 5 — Bezpieczeństwo i eksploatacja | I | I | C | A/R | C |
| Rozdz. 6 — Macierz śledzenia | I | C | C | C | A/R |
| Integracja dokumentu i PDF | C | I | I | I | A/R |
| Harmonogram, Issues, kontakt z Zamawiającym | A/R | I | I | I | I |
| Prezentacja i obrona | A | R | R | R | R |

**Zasady współpracy zespołu:** [kanał komunikacji, stały termin spotkań online, czas na recenzję PR (np. 48 h), sposób podejmowania decyzji przy braku zgody]

# 3. Architektura Systemu i Decyzje Technologiczne

<!--
Właściciel wiodący: Architekt Systemu. Termin: v0.9 (48 h przed Zjazdem 3); szkic na Zjeździe 2.
Minimum: C4 Context + C4 Container; stos technologiczny z uzasadnieniem; ≥ 3 ADR (w docs/adr/).
Typowe błędy: brak opisów relacji (strzałka bez etykiety i protokołu); "kontener" mylony z Dockerem;
stos wybrany "bo znamy" bez odniesienia do NFR; ADR bez alternatyw; aktorzy inni niż w rozdz. 2.1.
C4 rysujemy w Mermaid jako flowchart (stabilne renderowanie na GitHubie); składnia C4Context jest eksperymentalna.
-->

## 3.1. Architektura wysokopoziomowa — C4 Context (system w otoczeniu)

```mermaid
flowchart TB
    klient["👤 Klient<br/>[Osoba]<br/>Rezerwuje usługi"]
    pracownik["👤 Pracownik obsługi<br/>[Osoba]<br/>Obsługuje rezerwacje"]
    sys["[Nazwa systemu]<br/>[System — projektowany]<br/>Umożliwia …"]
    email["System e-mail<br/>[System zewnętrzny]<br/>np. usługa SMTP"]
    platnosci["Bramka płatności<br/>[System zewnętrzny]"]

    klient -- "Przegląda ofertę, rezerwuje<br/>[HTTPS]" --> sys
    pracownik -- "Zarządza rezerwacjami<br/>[HTTPS]" --> sys
    sys -- "Wysyła powiadomienia<br/>[SMTP]" --> email
    sys -- "Inicjuje płatność<br/>[REST/HTTPS]" --> platnosci

    classDef person fill:#08427b,color:#fff,stroke:#052e56
    classDef system fill:#1168bd,color:#fff,stroke:#0b4884
    classDef external fill:#999999,color:#fff,stroke:#6b6b6b
    class klient,pracownik person
    class sys system
    class email,platnosci external
```

**Opis:** [kto korzysta z systemu, z jakimi systemami zewnętrznymi się integruje i po co]

## 3.2. Architektura komponentowa — C4 Container

```mermaid
flowchart TB
    klient["👤 Klient [Osoba]"]

    subgraph granica["[Nazwa systemu]"]
        web["Aplikacja webowa<br/>[Kontener: SPA — technologia]<br/>Interfejs użytkownika"]
        api["API aplikacji<br/>[Kontener: technologia]<br/>Logika biznesowa, REST"]
        db[("Baza danych<br/>[Kontener: np. PostgreSQL]<br/>Dane rezerwacji, użytkowników")]
        worker["Usługa powiadomień<br/>[Kontener: technologia]<br/>Kolejka i wysyłka e-mail"]
    end

    email["System e-mail [System zewnętrzny]"]

    klient -- "Używa [HTTPS]" --> web
    web -- "Wywołuje API [JSON/HTTPS]" --> api
    api -- "Odczyt/zapis [SQL]" --> db
    api -- "Publikuje zdarzenia [kolejka]" --> worker
    worker -- "Wysyła [SMTP]" --> email

    classDef person fill:#08427b,color:#fff,stroke:#052e56
    classDef container fill:#438dd5,color:#fff,stroke:#2e6295
    classDef external fill:#999999,color:#fff,stroke:#6b6b6b
    class klient person
    class web,api,db,worker container
    class email external
```

| Kontener | Odpowiedzialność | Technologia | Komunikacja |
|---|---|---|---|
| [Aplikacja webowa] | [ ] | [ ] | [ ] |
| [API aplikacji] | [ ] | [ ] | [ ] |
| [Baza danych] | [ ] | [ ] | [ ] |
| [ ] | [ ] | [ ] | [ ] |

## 3.3. Stos technologiczny i uzasadnienie wyboru

| Warstwa | Wybór | Uzasadnienie (odwołanie do NFR / ograniczeń) | Rozważane alternatywy | ADR |
|---|---|---|---|---|
| Frontend | [ ] | [ ] | [ ] | ADR-001 |
| Backend / API | [ ] | [ ] | [ ] | ADR-001 |
| Baza danych | [ ] | [np. NFR-05 spójność transakcji → relacyjna] | [ ] | ADR-002 |
| Uwierzytelnianie | [ ] | [ ] | [ ] | ADR-003 |
| Protokoły / formaty | [REST + JSON, OpenAPI 3] | [ ] | [GraphQL, gRPC] | |
| Hosting / uruchomienie | [np. kontenery Docker w chmurze UE] | [ ] | [ ] | |

## 3.4. Kluczowe decyzje architektoniczne (ADR)

Pełna treść decyzji w katalogu [`adr/`](adr/README.md). Zestawienie:

| ID | Decyzja | Status | Powiązane wymagania |
|---|---|---|---|
| ADR-001 <!-- zamień na link, np. [ADR-001](adr/ADR-001-styl-architektury.md) --> | [np. Monolit modularny zamiast mikroserwisów] | przyjęta | [NFR-05, OGR-01] |
| ADR-002 | [ ] | [ ] | [ ] |
| ADR-003 | [ ] | [ ] | [ ] |

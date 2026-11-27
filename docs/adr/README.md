# Rejestr decyzji architektonicznych (ADR)

ADR (*Architecture Decision Record*) to krótki zapis jednej istotnej decyzji projektowej: kontekstu, rozważanych wariantów, wyboru i konsekwencji. Minimum w projekcie to **3 ADR**.

**Nowy ADR:** skopiuj [`ADR-000-szablon.md`](ADR-000-szablon.md) jako `ADR-NNN-krotki-opis.md`, uzupełnij go, dopisz wiersz poniżej i zgłoś PR z etykietą `adr`.

| ID | Tytuł | Status | Data | Powiązane wymagania |
|---|---|---|---|---|
| ADR-001 | [np. Styl architektury: monolit modularny] | [proponowana] | [ ] | [ ] |
| ADR-002 | [np. Relacyjna baza danych] | [ ] | [ ] | [ ] |
| ADR-003 | [np. Uwierzytelnianie: OpenID Connect + JWT] | [ ] | [ ] | [ ] |

**Przykładowe tematy decyzji:** styl architektury (monolit modularny / mikroserwisy), rodzaj bazy danych, framework frontendu i backendu, sposób uwierzytelniania, komunikacja synchroniczna lub asynchroniczna (kolejka), hosting (chmura / on-premise), integracja z systemem zewnętrznym (API / import plików), strategia kopii zapasowych.

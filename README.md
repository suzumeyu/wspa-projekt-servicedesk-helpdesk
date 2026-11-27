# ZAP-[NazwaZespolu] — [Nazwa systemu]

> Projekt systemu informatycznego realizowany w ramach przedmiotu **Zaawansowany projekt zespołowy cz. 1**.
> Produktem semestru jest **Zwarty Dokument Projektowy** (bez implementacji).

| | |
|---|---|
| **Temat** | nr [__] z listy tematów: [pełna nazwa tematu] |
| **Klient (Zamawiający)** | [organizacja z opisu tematu] — w roli Zamawiającego: prowadzący zajęcia |
| **Grupa zajęciowa** | [G1 / G2] |
| **Bieżąca wersja** | [v0.1 / v0.5 / v0.9 / v1.0] — patrz [Releases](../../releases) |
| **Status** | [w opracowaniu / do przeglądu / do odbioru / odebrany / odebrany warunkowo] |

## Zespół

| Imię i nazwisko | Rola | Login GitHub |
|---|---|---|
| [ ] | Project Manager | @[ ] |
| [ ] | Analityk Biznesowy | @[ ] |
| [ ] | Architekt Systemu | @[ ] |
| [ ] | Projektant Danych i Bezpieczeństwa | @[ ] |
| [ ] | QA / Tech Writer | @[ ] |

## Cel systemu (2–3 zdania)

[Dla kogo powstaje system, jaki problem rozwiązuje i jaka jest najważniejsza korzyść biznesowa.]

## Zwarty Dokument Projektowy

| Rozdz. | Plik | Właściciel | Status |
|---|---|---|---|
| — | [Strona tytułowa, historia zmian, spis treści](docs/00_zwarty_dokument.md) | QA / Tech Writer | ☐ |
| 1 | [Karta Projektu i Uzasadnienie Biznesowe](docs/01_karta_projektu.md) | PM | ☐ |
| 2 | [Specyfikacja Wymagań Systemowych](docs/02_wymagania.md) | Analityk + QA | ☐ |
| 3 | [Architektura Systemu i Decyzje Technologiczne](docs/03_architektura.md) | Architekt | ☐ |
| 4 | [Szczegółowy Projekt Danych i Logiki](docs/04_dane_i_logika.md) | Projektant Danych + Architekt | ☐ |
| 5 | [Bezpieczeństwo, Infrastruktura i Eksploatacja](docs/05_bezpieczenstwo_eksploatacja.md) | Projektant Danych i Bezpieczeństwa | ☐ |
| 6 | [Matryca Śledzenia Wymagań](docs/06_macierz_sledzenia.md) | QA / Tech Writer | ☐ |
| — | [Rejestr decyzji architektonicznych (ADR)](docs/adr/README.md) | Architekt | ☐ |

Statusy: ☐ nie rozpoczęto · ◐ w opracowaniu · ☑ zrecenzowane i scalone.

## Struktura repozytorium

```text
/
├── README.md                 ← ten plik
├── CONTRIBUTING.md           ← zasady pracy zespołu (gałęzie, PR, recenzje)
├── CHANGELOG.md              ← historia wersji (tagów)
├── .github/                  ← szablony PR i Issues
└── docs/
    ├── 00_zwarty_dokument.md ← scalenie rozdziałów do PDF
    ├── 01_karta_projektu.md … 06_macierz_sledzenia.md
    ├── adr/                  ← ADR-001, ADR-002 …
    ├── diagramy/             ← źródła diagramów spoza Mermaid (.drawio, .puml, .bpmn)
    ├── img/                  ← eksporty diagramów (SVG/PNG)
    └── zalaczniki/           ← prezentacja i protokół odbioru; makiety (opcjonalnie)
```

## Pierwsze 15 minut (Zjazd 1) — instrukcja dla zespołu

1. **PM:** *Use this template → Create a new repository*, nazwa `ZAP-[NazwaZespolu]`, widoczność **Public** (zalecane).
2. **PM:** *Settings → Collaborators*: dodaj wszystkich członków zespołu oraz prowadzącego `@wmwspa`. Każdy przyjmuje zaproszenie.
3. **PM:** *Settings → Branches*: ochrona `main` (wymagany PR + 1 zatwierdzenie). Szczegóły: G03, rozdz. 1.3.
4. **PM:** utwórz etykiety (`rozdz-1` … `rozdz-6`, `adr`, `recenzja`, `uwaga-prowadzacego`, `uwaga-odbioru`, `blokada`, `pytanie-do-klienta`) i kamienie milowe (`v0.5 – Zjazd 2`, `v0.9 – Zjazd 3`, `v1.0 – Odbiór` — termin 48 h przed sesją odbiorczą).
5. **Każdy:** otwórz repozytorium w przeglądarce, naciśnij **`.`** (github.dev) lub sklonuj je lokalnie, utwórz gałąź `feature/rozgrzewka-<login>`, uzupełnij swój wiersz w tabeli **Zespół** powyżej i zgłoś PR.
6. **Każdy:** zrecenzuj PR kolejnej osoby z listy i zatwierdź go (*Approve*).
7. **Zespół:** uzupełnij w `docs/01_karta_projektu.md` cel, zakres (In/Out-of-Scope) i w `docs/02_wymagania.md` ≥ 5 User Stories (Must) → PR → merge → **tag `v0.1`**.

Pełny opis zasad: [CONTRIBUTING.md](CONTRIBUTING.md).

---

<sub>Wszystkie dane w projekcie (osoby, organizacje, liczby) są fikcyjne i służą wyłącznie celom dydaktycznym.</sub>

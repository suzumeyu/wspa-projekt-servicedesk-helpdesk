# Zasady pracy w repozytorium

Skrót zasad przedmiotu. Pełna wersja: materiał **G03 — Workflow zespołu w projekcie**.

## 1. Gałąź `main` jest chroniona

- Do `main` trafiają zmiany **wyłącznie przez Pull Request** z co najmniej **1 zatwierdzeniem** innej osoby z zespołu.
- Zakazane: commit bezpośrednio do `main`, `git push --force`, usuwanie `main`.

## 2. Cykl pracy

1. **Issue** (szablon *Zadanie*): jedna osoba odpowiedzialna, etykieta rozdziału, kamień milowy.
2. **Gałąź:** `git switch main && git pull && git switch -c feature/<obszar>-<opis>`
   (przykłady: `feature/karta-raci`, `feature/proces-rezerwacji`, `feature/erd`, `feature/adr-002-baza-danych`).
3. **Commity:** małe kroki, prefiks:
   - `docs:` nowa lub rozszerzona treść — `docs: dodano FR-06…FR-10`,
   - `fix:` poprawka — `fix: ujednolicono nazwę encji Uczestnik`,
   - `chore:` porządki — `chore: dodano etykiety i milestone`.
4. **Pull Request:** wypełniony szablon, w opisie `Closes #<nr Issue>`, wskazany recenzent.
5. **Recenzja** w ciągu 48 h: lista kontrolna z szablonu PR i G03. *Approve* albo *Request changes*.
6. **Squash and merge** przez autora po zatwierdzeniu. Gałąź usuwa się automatycznie.

## 3. Treść i pliki

- Każdy rozdział to osobny plik w `docs/`. Każda decyzja architektoniczna to osobny plik w `docs/adr/`.
- Identyfikatory: `INT-01` (interesariusz), `ACT-01` (aktor), `PROC-01` (proces), `FR-01`, `NFR-01`, `ADR-001`, `SEQ-01` (sekwencja), `R-01` (ryzyko), `CEL-01` (miernik celu), `MOD-01` / `OUT-01` (zakres In/Out), `ZAL-01` / `OGR-01` (założenie / ograniczenie), `API-01` (endpoint), `DR-01` (scenariusz awaryjny), `UI-01` (makieta). **Raz nadanego ID nie zmieniamy.** Usunięte wymaganie oznaczamy jako *wycofane*, a numer nie wraca do puli.
- Nazwy aktorów, encji, statusów i procesów są identyczne we wszystkich rozdziałach.
- Diagramy domyślnie w Mermaid. Źródła z innych narzędzi trafiają do `docs/diagramy/`, a eksport SVG/PNG do `docs/img/`.
- Każdy PR, który dodaje lub zmienia wymaganie albo element projektu, **aktualizuje macierz śledzenia** (`docs/06_macierz_sledzenia.md`).
- Do repozytorium nie trafiają: hasła, tokeny, prawdziwe dane osobowe, pliki PDF/DOCX. PDF dokumentu dołączamy do **GitHub Release**. Wyjątki: `docs/zalaczniki/prezentacja.pdf` (prezentacja na sesję odbiorczą) i ewentualnie podpisany `docs/zalaczniki/protokol_odbioru.pdf`.

## 4. Wersje

| Tag | Termin |
|---|---|
| `v0.1` | koniec Zjazdu 1 |
| `v0.5` | 48 h przed Zjazdem 2 (rozdz. 1–2) |
| `v0.9` | 48 h przed Zjazdem 3 (rozdz. 1–6) |
| `v1.0` | 48 h przed sesją odbiorczą (zdalną) — wersja odbierana + PDF w Release |
| `v1.1` | do 7 dni po sesji odbiorczej, tylko przy odbiorze warunkowym |

Tag zakłada PM na `main` po scaleniu wszystkich PR etapu (`git tag -a v0.5 -m "…"` → `git push origin v0.5`) i uzupełnia `CHANGELOG.md`.

## 5. Komunikacja

- Ustalenia merytoryczne zapisujemy w Issues i PR, nie wyłącznie na komunikatorze. Co nie jest zapisane w repozytorium, tego nie ustalono.
- Problem techniczny trwający dłużej niż 30 minut zgłaszamy jako Issue z etykietą `blokada`.
- Pytania do Zamawiającego (prowadzącego) zgłaszamy jako Issues z etykietą `pytanie-do-klienta` i oznaczamy w nich `@wmwspa`.

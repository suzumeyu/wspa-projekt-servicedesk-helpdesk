# PROJEKT SYSTEMU INFORMATYCZNEGO: [NAZWA SYSTEMU]

**Dokumentacja Projektowa Techniczna** | Wersja: [1.0] | Data: [RRRR-MM-DD]

**Zespół Wykonawczy:** [Nazwa/Numer Zespołu] | **Grupa:** [G1/G2] | **Repozytorium:** [https://github.com/…/ZAP-NazwaZespolu]

**Zamawiający:** [Organizacja z opisu tematu] (w roli Zamawiającego: prowadzący zajęcia)
**Przedmiot:** Zaawansowany projekt zespołowy cz. 1

| Rola | Imię i nazwisko |
|---|---|
| Project Manager | [ ] |
| Analityk Biznesowy | [ ] |
| Architekt Systemu | [ ] |
| Projektant Danych i Bezpieczeństwa | [ ] |
| QA / Tech Writer | [ ] |

<!--
Ten plik służy dwóm celom:
1) na GitHubie — strona tytułowa, historia zmian i spis treści z linkami do rozdziałów,
2) w VS Code z rozszerzeniem "Markdown Preview Enhanced" (MPE) — scalenie wszystkich rozdziałów do jednego PDF.
   Dyrektywy @import na końcu pliku działają TYLKO w MPE; na GitHubie wyświetlą się jako zwykły tekst — to zamierzone.
   Eksport: podgląd MPE → prawy przycisk → Export → Chrome (Puppeteer) → PDF. Szczegóły: G03, rozdz. 7.
PDF NIE jest commitowany (.gitignore) — dołączamy go do GitHub Release v1.0.
-->

## Historia zmian

| Wersja | Data | Autor(zy) | Zakres zmian | Recenzent |
|---|---|---|---|---|
| 0.1 | [ ] | [ ] | Karta projektu v0.1, pierwsze User Stories | [ ] |
| 0.5 | [ ] | [ ] | Rozdz. 1–2 kompletne | [ ] |
| 0.9 | [ ] | [ ] | Rozdz. 3–6, poprawki po przeglądzie v0.5 | [ ] |
| 1.0 | [ ] | [ ] | Wersja do odbioru, poprawki po recenzji krzyżowej i autokontroli | [ ] |

## Spis treści

1. [Karta Projektu i Uzasadnienie Biznesowe](01_karta_projektu.md)
2. [Specyfikacja Wymagań Systemowych](02_wymagania.md)
3. [Architektura Systemu i Decyzje Technologiczne](03_architektura.md)
4. [Szczegółowy Projekt Danych i Logiki](04_dane_i_logika.md)
5. [Bezpieczeństwo, Infrastruktura i Eksploatacja](05_bezpieczenstwo_eksploatacja.md)
6. [Matryca Śledzenia Wymagań (Traceability Matrix)](06_macierz_sledzenia.md)

Załączniki: [Rejestr decyzji architektonicznych (ADR)](adr/README.md) · [Makiety (opcjonalnie)](zalaczniki/README.md)

<div style="page-break-after: always;"></div>

<!-- ===== Scalenie rozdziałów do PDF (Markdown Preview Enhanced) ===== -->

@import "01_karta_projektu.md"

<div style="page-break-after: always;"></div>

@import "02_wymagania.md"

<div style="page-break-after: always;"></div>

@import "03_architektura.md"

<div style="page-break-after: always;"></div>

@import "04_dane_i_logika.md"

<div style="page-break-after: always;"></div>

@import "05_bezpieczenstwo_eksploatacja.md"

<div style="page-break-after: always;"></div>

@import "06_macierz_sledzenia.md"

<div style="page-break-after: always;"></div>

## Załącznik A. Rejestr decyzji architektonicznych

@import "adr/README.md"

<!-- Dopisz poniżej (poza komentarzem, od początku linii) dyrektywę dla każdego utworzonego ADR, np. @import "adr/ADR-001-styl-architektury.md" -->

<!-- Opcjonalnie — makiety: dopisz poniżej (poza komentarzem, od początku linii) @import "zalaczniki/README.md" -->

## Załącznik B. Recenzje i odbiór

Rejestr uwag z recenzji krzyżowej i od Zamawiającego: Issues z etykietami `recenzja`, `uwaga-prowadzacego` i `uwaga-odbioru` w repozytorium. Protokół zdawczo-odbiorczy: `zalaczniki/protokol_odbioru.md`, zaakceptowany na sesji odbiorczej w PR nr [#… — uzupełnia PM].

# Źródła diagramów spoza Mermaid

Domyślnie diagramy tworzymy w **Mermaid** bezpośrednio w plikach rozdziałów. Ten katalog jest przeznaczony dla diagramów z innych narzędzi.

| Narzędzie | Plik źródłowy (tutaj) | Eksport (w `../img/`) |
|---|---|---|
| draw.io / diagrams.net (także rozszerzenie VS Code *Draw.io Integration*) | `.drawio` (lub `.drawio.svg`) | `.svg` |
| PlantUML | `.puml` | `.svg` |
| Camunda Modeler / bpmn.io (BPMN 2.0) | `.bpmn` | `.svg` / `.png` |

**Zasady:**

1. Nazwa pliku zawiera identyfikator diagramu: `proc-02-reklamacja.drawio` → `../img/proc-02-reklamacja.svg`.
2. Źródło i eksport zmieniamy **w tym samym PR**.
3. W rozdziale wstawiamy eksport: `![PROC-02 Obsługa reklamacji](img/proc-02-reklamacja.svg)` z podpisem i opisem.
4. Zrzuty ekranu bez pliku źródłowego są niedopuszczalne, bo nie da się ich zrecenzować ani poprawić.

## Wykaz

| ID diagramu | Plik źródłowy | Eksport | Rozdział |
|---|---|---|---|
| [ ] | [ ] | [ ] | [ ] |

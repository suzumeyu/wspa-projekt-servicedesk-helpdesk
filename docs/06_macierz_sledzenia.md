# 6. Matryca Śledzenia Wymagań (Traceability Matrix)

<!--
Właściciel wiodący: QA / Tech Writer. Aktualizuje ją autor każdego PR zmieniającego wymagania lub elementy projektu.
Minimum: 100% FR "Must" i 100% NFR ma powiązanie z co najmniej jednym elementem architektury/danych/sekwencji.
Typowe błędy: macierz uzupełniana w ostatniej chwili i niezgodna z treścią; ID nieistniejące w rozdziałach;
"osierocone" wymagania (brak realizacji) lub "osierocone" elementy projektu (brak wymagania, które uzasadnia ich istnienie).
-->

## 6.1. Wymagania funkcjonalne

| ID Wymagania | Opis skrócony | Priorytet | Proces | Element Architektury (C4/API) | Tabela w ERD | Diagram Sekwencji | Cel (CEL) |
| :--- | :--- | :---: | :--- | :--- | :--- | :--- | :--- |
| FR-01 | [Utworzenie rezerwacji] | Must | PROC-01 | API aplikacji / API-02 | REZERWACJA, TERMIN | SEQ-01 | CEL-01 |
| FR-02 | [ ] | Must | | | | | |
| FR-03 | [ ] | Must | | | | | |
| … | | | | | | | |

## 6.2. Wymagania niefunkcjonalne

| ID Wymagania | Opis skrócony | Element architektury / rozwiązanie | Rozdział / ADR | Sposób weryfikacji |
| :--- | :--- | :--- | :--- | :--- |
| NFR-01 | [czas odpowiedzi < 500 ms] | [indeksy na TERMIN(poczatek), cache listy terminów] | 4.1, ADR-00x | test obciążeniowy |
| NFR-02 | [ ] | [ ] | 5.1 | |
| … | | | | |

## 6.3. Kontrola pokrycia

| Miara | Wartość |
|---|---|
| Liczba FR Must / pokrytych | [ ] / [ ] |
| Liczba NFR / pokrytych | [ ] / [ ] |
| Elementy architektury bez powiązanego wymagania | [lista lub „brak”] |
| Tabele ERD bez powiązanego wymagania | [lista lub „brak”] |

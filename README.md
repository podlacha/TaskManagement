# Zadanie rekrutacyjne
Prosty system do zarządzania zadaniami - część bazodanowa.
## Opis
System ma służyć do zarządzania zadaniami. Użytkownicy są podzieleni na dwie grupy: podstawowych (pracownicy) i menadżerów. Użytkownik może dodawać, edytować i usuwać zadania.
Każdy użytkownik ma dostęp do swoich zadań oraz zadań udostępnionych przez innych. Menadżerowie mają dodatkowo możliwość przeglądania zadań swoich podwładnych.
Menadżer powinien mieć także możliwość zobaczenia statystyk zadań z podziałem na miesiące: podwładny, status, liczba zadań.
Zadanie z danymi typu nagłówek, priorytet, opis. Powinna być możliwość przejrzenia historii zmian zadań.
Zadania i logika są przechowywane w bazie danych SQL Server. Dostęp za pomocą procedur składowanych.
Załóż, że system może pracować dla wielu niezależnych podmiotów (architektura multitenant) oraz że liczba użytkowników i zadań będzie bardzo szybko przyrastać w czasie
a ważna jest responsywność działania systemu (będą miliony wierszy).
Twoim zadaniem jest zaprojektować struktury danych oraz procedury z logiką biznesową i inne obiekty jeżeli potrzeba.
Napisz skrypt generujący po 100 testowych userów dla 10 podmiotów oraz 1000 zadań dla każdego użytkownika.
Rozwiązanie udostępnij w formie linku do repozytorium git ze skryptami tworzącymi struktury/obiekty.
*) Jeżeli uważasz, że brakuje Ci informacji do opracowania rozwiązania, dopisz założenia według uznania i zamieść je w Readme.
**) Jeżeli nie potrafisz (nie masz czasu) zaimplementować wszystkiego, nie szkodzi. Zrób ile potrafisz. Opisz co Twoim zdaniem trzeba jeszcze zrobić.
***) Zapisz decyzje architektoniczne pozwalające zrozumieć zastosowane rozwiązanie czy uproszczenia.
### Struktura
Tabela -> Tabela użytkowników -> Tabela zadań ->

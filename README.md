# Zadanie rekrutacyjne
Prosty system do zarządzania zadaniami - część bazodanowa.
## Opis
System ma służyć do zarządzania zadaniami. Użytkownicy są podzieleni na dwie grupy: podstawowych (pracownicy) i menedżerów. Użytkownik może dodawać, edytować i usuwać zadania.
Każdy użytkownik ma dostęp do swoich zadań oraz zadań udostępnionych przez innych. Menedżerowie mają dodatkowo możliwość przeglądania zadań swoich podwładnych.
Menedżer powinien mieć także możliwość zobaczenia statystyk zadań z podziałem na miesiące: podwładny, status, liczba zadań.
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
## Struktura główna
Tabela dla podmiotów -> Tabela dla użytkowników -> Tabela przypisująca użytkowników do menedżerów -> Tabela dla zadań -> Tabela historii zmian
## Podląd statystyk dla menedżerów
Dodałem podgląd statystyk dla menedżerów. Moja ograniczona w tym momencie wiedza w zakresie SQL-a nie pozwala mi ocenić czy do statystyk powinienem dodać również odrębną tabelę. Nie mam też możliwości przetestowania skryptu.
Nie mam pewności czy nie powinienem dodać odrębnej tabeli dat (z podziałem na miesiące). Na zajęciach z Power BI tworzyliśmy tabelę dat do generowania statystyk.
## Usprawnienia
Aby usprawnić działanie skryptu (szybki rozwój struktury) zaproponowałem indeksowanie oraz partycjonowanie zadań na lata.
## Przypisanie ról użytkownikom
W celu przypisania ról użytkownikom utworzyłem Tabelę, a także procedurę pobierania zadań z filtrami, która powinna powodować, że menedżer ma dostęp tylko do zadań swoich i swoich podwładnych, a nie całego podmiotu.
## Kolejny etap
Kolejnym etapem powinno być przetestowanie kodu, czy wszystko działa zgodnie z założeniami.

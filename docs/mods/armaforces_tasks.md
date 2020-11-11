# TASKI

## O taskach

Framework zadań. Automatyczne tworzenie tasków (zadań) na bazie mission config. Wszystkie skrypty, warunki, i eventy uruchamiane są tylko po stronie serwera.

## Jak korzystać

Utwórz klasę **CfgTasks** w pliku **description.ext** swojej misji i wypełnij ją taskami. Tyle wystarczy!
Jeżeli nie planujesz wykorzystać którejś z property (właściwości) usuń ją, zamiast zostawiać wpis pusty. W innym wypadku mogą dziać się rzeczy niestworzone.

## Właściwości tasków (properties)

- title - nazwa taska
- description - opis taska. Nie wykorzystuje łamania tekstu (poprzez klawisz enter), w przypadku konieczności użycia należy skorzystać ze stringtable.
- marker - sprawdza istnienie markera o takiej nazwie, jeżeli istnieje umieszcza w tej lokalizacji task. Jeżeli nie istnieje, patrz punkt niżej.
- object - sprawdza istnienie obiektu o takiej nazwie w namespace'ie misji.
- position[] - alternatywny sposób umieszczania misji, poprzez podanie koordynatów {x, y, z}.
- icon - odpowiada za obrazek taska na mapie, [więcej informacji](https://community.bistudio.com/wiki/Arma_3_Task_Framework#Task_icons).
- 

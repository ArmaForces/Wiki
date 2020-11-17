# TASKI

## O taskach

Framework zadań. Automatyczne tworzenie tasków (zadań) na bazie mission config. Wszystkie skrypty, warunki, i eventy uruchamiane są tylko po stronie serwera.

## Jak korzystać

Utwórz klasę **CfgTasks** w pliku **description.ext** swojej misji i wypełnij ją taskami. Tyle wystarczy!
Jeżeli nie planujesz wykorzystać którejś z properties (parametrów) usuń wpis, zamiast zostawiać go pustym. W innym wypadku mogą dziać się rzeczy niestworzone.

## Parametry tasków (properties)

Poniższy kod przedstawia możliwe do wykorzystania 

```sqf
class CfgTasks {
    class Soapy_Mission_XD {
        title = "Soapy Mission XD - Horse Knocked"; // Nazwa taska
        description = "Great mission of beating horse."; // Opis taska. Nie korzysta z łamaczy tekstu (klawisz enter). Jeżeli jest ci to potrzebne, użyj stringtable.
        /* Ikona taska na mapie
        Najpierw następuje sprawdzenie, czy znacznik/marker o danej nazwie istnieje. Jeżeli nie istnieje, to wyszukuje obiektu w namespace'ie misji.
        Alternatywnym rozwiązaniem jest dostarczenie kooordynatów {x, y, z}.
        Jeżeli nie pojawi się żaden z tych wpisów, to task będzie na mapie niewidoczny.*/
        position[] = {}; // Do wykorzystania przy podawaniu konkretnych koordynatów
        object = ""; // Do wykorzystanie dla obiektów
        marker = ""; // Do wykorzystania dla nazw znaczników/markerów
        icon = "unknown"; // Icon TUTAJ POPRAWIC classname TUTAJ POPRAWIC from TUTAJ POPRAWIC https://community.bistudio.com/wiki/Arma_3_Tasks_Overhaul#Appendix TUTAJ POPRAWIC
        owners[] = { "true" }; // Domyślna wartość, wpisz "All"/"true", aby task był dostepny dla wszystkich grających.
        initialState = "CREATED"; // Domyślna wartość
        priority = -1; // Domyślna wartość
        createdShowNotification = "false"; // Domyślna wartość
        visibleIn3D = "false"; // Domyślna wartość

        parentTask = ""; // Config entry name of parent task

        // Pokazywanie/tworzenie taska
        conditionCodeShow = "true";
        conditionEventsShow[] = {}; // Domyślna wartość dla wszystkich conditionEvents*[] jest równa [] co przekłada się na {} w configu.
        conditionEventsShowRequired = 1; // Ile eventów musi się uruchomić, aby spełnić warunek eventów.

        // Kody warunków, które musza zwracać true, aby zakończyć task
        conditionCodeSuccess = ""; // Task udany
        conditionCodeFailed = ""; // Task spartaczony
        conditionCodeCanceled = ""; // Task anulowany
        // Kody eventów CBA, które muszą być odpalone, żeby osiagnąć to co wyżej
        conditionEventsSuccess[] = {};
        conditionEventsFailed[] = {};
        conditionEventsCanceled[] = {};
        // And number required as in show but for all others 
        conditionEventsSuccessRequired = 1;
        conditionEventsFailedRequired = 1;
        conditionEventsCanceledRequired = 1;

        // Server CBA events called. If you want custom code just add appropriate CBA EH on server. // 
        onShowEvents[] = {};
        onSuccessEvents[] = {};
        onFailedEvents[] = {};
        onCanceledEvents[] = {};
    };
    class FindHorse {
        title = "Find Horse";
        icon = "search";
        parentTask = "Soapy_Mission_XD";
        conditionCodeShow = "true";
        conditionCodeSuccess = "unit1 distance horse < 50";
        onSuccessEvents[] = { "horseFound" };
    };
    class KnockHorse {
        title = "Knock Horse";
        icon = "attack";
        object = "horse";
        parentTask = "FindHorse";

        conditionEventsShow[] = { "horseFound" };
        conditionCodeSuccess = "!(alive horse)";
        conditionCodeFailed = "!(alive unit1)";

        onSuccessEvents[] = { "horseKnocked" };
        onFailedEvents[] = { "playerDied" };
    };
};
```

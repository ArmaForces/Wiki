# TASKI

## O taskach

Framework zadań - szkielet, w oparciu o który możecie tworzyć swoje super misje, które na pewno sprostają oczekiwaniom. Automatyczne tworzenie tasków (zadań) na bazie mission config. Wszystkie skrypty, warunki, i eventy uruchamiane są tylko po stronie serwera.

## Jak korzystać

Utwórz klasę **CfgTasks** w pliku **description.ext** swojej misji i wypełnij ją taskami. Tyle wystarczy!
Jeżeli nie planujesz wykorzystać którejś z properties (parametrów) usuń wpis, zamiast zostawiać go pustym. W innym wypadku mogą dziać się rzeczy niestworzone. Uwaga - są to rzeczy relatywnie skomplikowane dla zupełnego laika, więc należy je przeanalizować sumiennie i ze zrozumieniem - nie zalecam podchodzić do tego z podejściem "raz przeczytam i będę umiał", jeżeli masz zerowe doświadczenie.

## Parametry tasków (properties)

Poniższy kod przedstawia możliwe do wykorzystania properties. Są częściami składowymi tasków, więc należy zrozumieć, za co poszczególne z nich odpowiadają - część z może być gorzej opisana, najlepiej jest wtedy zostawić wartość domyślną, która jest już podana przy zmiennych.

```hpp
class CfgTasks {
    class Soapy_Mission_XD {
        title = "Soapy Mission XD - Horse Knocked"; // Nazwa taska
        description = "Great mission of beating horse."; // Opis taska. Nie korzysta z łamaczy tekstu (klawisz enter). Jeżeli jest ci to potrzebne, użyj stringtable.
        /* Ikona taska na mapie
        Najpierw następuje sprawdzenie, czy znacznik/marker o danej nazwie istnieje. Jeżeli nie istnieje, to wyszukuje obiektu w namespace'ie misji.
        Alternatywnym rozwiązaniem jest dostarczenie kooordynatów {x, y, z}.
        Jeżeli nie pojawi się żaden z tych wpisów, to task będzie na mapie niewidoczny.*/
        position[] = {}; // Do wykorzystania przy podawaniu konkretnych koordynatów
        object = ""; // Do wykorzystanie dla nazwy obiektu
        marker = ""; // Do wykorzystania dla nazwy znacznika/markera
        icon = "unknown"; // jak ikonka ma wyglądać na mapie - https://community.bistudio.com/wiki/Arma_3_Task_Framework#Task_icons - tutaj znajdziecie wylistowane możliwości.
        owners[] = { "true" }; // Domyślna wartość "All"/"true" pokazuje zadanie wszystkim graczom.
        initialState = "CREATED"; // Domyślna wartość
        priority = -1; // Domyślna wartość
        createdShowNotification = "false"; // Domyślna wartość
        visibleIn3D = "false"; // Domyślna wartość
        parentTask = ""; // Umożliwia wskazanie zadania nadrzędnego

        // Pokazywanie/tworzenie taska
        conditionCodeShow = "true";
        conditionEventsShow[] = {}; // Domyślna wartość dla wszystkich conditionEvents*[] jest równa [] co przekłada się na {} w configu.
        conditionEventsShowRequired = 1; // Ile eventów musi się uruchomić, aby spełnić warunek uruchomienia eventów.

        // Kody warunków, które musza zwracać true, aby zakończyć task
        conditionCodeSuccess = ""; // Task udany
        conditionCodeFailed = ""; // Task spartaczony
        conditionCodeCanceled = ""; // Task anulowany
        // Kody eventów CBA, które muszą być odpalone, żeby  zakończyć task
        conditionEventsSuccess[] = {}; // Task udany
        conditionEventsFailed[] = {}; // Task spartaczony
        conditionEventsCanceled[] = {}; // Task anulowany
        // Ile eventów z odpowiadającej listy musi zostać wywołanych aby zadanie zostało zakończone w określony sposób
        conditionEventsSuccessRequired = 1;  // Task udany
        conditionEventsFailedRequired = 1; // Task spartaczony
        conditionEventsCanceledRequired = 1; // Task anulowany

        // Wywoływanie eventów CBA. Wywoływanie customowych zdarzeń i kodu odbywa się przez dodanie odpowiednich event handlerów CBA na serwerze - patrz niżej.
        onShowEvents[] = {}; // eventy wywoływane przy ujawnieniu taska
        onSuccessEvents[] = {}; // eventy wywoływane przy sukcesie taska
        onFailedEvents[] = {}; // eventy wywoływane przy spartaczeniu, porażce taska
        onCanceledEvents[] = {}; // eventy wywoływane przy anulowaniu taska
    };

    // definiujemy taski podrzędne
    class FindHorse { // nazwa klasy taska
        title = "Znajdź kunia"; // Tytuł taska
        icon = "search"; // ikona, którą zobaczą na tasku gracze
        parentTask = "Soapy_Mission_XD"; // Task nadrzędny, odwołanie następuje po nazwie klasy
        conditionCodeShow = "true"; // Task będzie od razu widoczny dla graczy na liście tasków
        conditionCodeSuccess = "unit1 distance horse < 50"; // Sukces taska nastąpi w momencie, kiedy dystans między obiektami unit1 oraz horse < 50
        onSuccessEvents[] = { "horseFound" }; // event wywoływany zaliczeniem taska (odwołanie nastąpi nieco niżej, czytajcie uważnie)
    };
    class KnockHorse { 
        title = "Zwal kunia"; 
        icon = "attack"; 
        object = "horse"; // Wskazuje nazwę konkretnego obiektu, za którym będzie podążał task na mapie
        parentTask = "FindHorse";

        conditionEventsShow[] = { "horseFound" }; // warunek, który musi być spełniony, by task się pojawił. Patrz onSuccessEvents[] dla zadania FindHorse
        conditionCodeSuccess = "!(alive horse)"; // by zaszło zwycięstwo obiekt "horse" ma być martwy (negacją jest znak "!")
        conditionCodeFailed = "!(alive unit1)"; // by zaszła porażka obiekt "unit1" ma być martwy

        onSuccessEvents[] = { "horseKnocked" }; // event wywołany udanym zakończeniem taska, przykład obsługi w rozdziale "Przykładowy niestandardowy event handling"
        onFailedEvents[] = { "playerDied" }; // event wywołany porażką taska, przykład obsługi w rozdziale "Przykładowy niestandardowy event handling"
    };
};
```

## Przykładowy niestandardowy event handling 

```sqf
// kod wprowadzamy w pliku initServer.sqf

// Event handler dla udanego taska (onSuccessEvents)
["horseKnocked", { // nazwa eventu wywoływana w description.ext
    titleText ["You beat the horse!", "PLAIN DOWN", 0.5];
    [{
        "EveryoneWon" call BIS_fnc_endMission;
    }, [], 3] call CBA_fnc_waitAndExecute;
}] call CBA_fnc_addEventHandler;

// Event handler dla nieudanego taska (onFailedEvents)
["playerDied", { // nazwa eventu wywoływana w description.ext
    titleText ["You died!", "PLAIN DOWN", 0.5];
    [{
        "EveryoneLost" call BIS_fnc_endMission;
    }, [], 3] call CBA_fnc_waitAndExecute;
}] call CBA_fnc_addEventHandler;
```

## Framework events

Zaawansowana obsługa eventów CBA wywoływanych przez framework tasków. Dostępne są 2 eventy:

- `afm_tasks_taskCreated` wywoływany jest gdy zadanie zostaje utworzone (czyli w momencie spełnienia warunku utworzenia zadania). Jako parametr posiada nazwę klasy zadania, które zostało utworzone.
- `afm_tasks_taskStateChanged` wywoływany jest, gdy zadanie zmieni swój stan. Jako parametry posiada nazwę klasy zadania oraz nowy stan zadania.

```
Event "afm_tasks_taskCreated"
  Params
  - 0: Task config name <STRING>
Event "afm_tasks_taskStateChanged"
  Params
  - 0: Task config name <STRING>
  - 1: New task state <STRING>
```

### Autorzy
- [3Mydło3](http://github.com/3Mydlo3)

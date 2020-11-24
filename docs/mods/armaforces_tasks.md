# TASKI

## O taskach

Framework zadań. Automatyczne tworzenie tasków (zadań) na bazie mission config. Wszystkie skrypty, warunki, i eventy uruchamiane są tylko po stronie serwera.

## Jak korzystać

Utwórz klasę **CfgTasks** w pliku **description.ext** swojej misji i wypełnij ją taskami. Tyle wystarczy!
Jeżeli nie planujesz wykorzystać którejś z properties (parametrów) usuń wpis, zamiast zostawiać go pustym. W innym wypadku mogą dziać się rzeczy niestworzone.

## Parametry tasków (properties)

Poniższy kod przedstawia możliwe do wykorzystania properties. Są częściami składowymi tasków, więc należy zrozumieć, za co poszczególne z nich odpowiadają - część z może być gorzej opisana, najlepiej jest wtedy zostawić wartość domyślną, która jest podana.

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
        object = ""; // Do wykorzystanie dla nazw obiektów
        marker = ""; // Do wykorzystania dla nazw znaczników/markerów
        icon = "unknown"; // Icon TUTAJ POPRAWIC classname TUTAJ POPRAWIC from TUTAJ POPRAWIC https://community.bistudio.com/wiki/Arma_3_Tasks_Overhaul#Appendix TUTAJ POPRAWIC
        owners[] = { "true" }; // Domyślna wartość, wpisz "All"/"true", aby task był dostepny dla wszystkich grających.
        initialState = "CREATED"; // Domyślna wartość
        priority = -1; // Domyślna wartość
        createdShowNotification = "false"; // Domyślna wartość
        visibleIn3D = "false"; // Domyślna wartość
        parentTask = ""; // Do konfigurowania nazwy taska nadrzędnego

        // Pokazywanie/tworzenie taska  TUTAJ TUTAJ TUTAJ TUTAJ TUTAJ
        conditionCodeShow = "true";
        conditionEventsShow[] = {}; // Domyślna wartość dla wszystkich conditionEvents*[] jest równa [] co przekłada się na {} w configu.
        conditionEventsShowRequired = 1; // Ile eventów musi się uruchomić, aby spełnić warunek eventów.

        // Kody warunków, które musza zwracać true, aby zakończyć task
        conditionCodeSuccess = ""; // Task udany
        conditionCodeFailed = ""; // Task spartaczony
        conditionCodeCanceled = ""; // Task anulowany
        // Kody eventów CBA, które muszą być odpalone, żeby osiagnąć to co wyżej
        conditionEventsSuccess[] = {}; // Task udany
        conditionEventsFailed[] = {}; // Task spartaczony
        conditionEventsCanceled[] = {}; // Task anulowany
        // Ile eventów musi zakończyć się sukcesem/porażką/anulowaniem, TUTAJ TUTAJ TUTAJ TUTAJ TUTAJ 
        conditionEventsSuccessRequired = 1; 
        conditionEventsFailedRequired = 1;
        conditionEventsCanceledRequired = 1;

        // Server CBA events called. If you want custom code just add appropriate CBA EH on server. // 
        onShowEvents[] = {}; // eventy wywoływane przy ujawnieniu taska
        onSuccessEvents[] = {}; // eventy wywoływane przy sukcesie taska
        onFailedEvents[] = {}; // eventy wywoływane przy spartaczeniu, porażce taska
        onCanceledEvents[] = {}; // eventy wywoływane przy anulowaniu taska
    };
    class FindHorse { // nazwa klasy
        title = "Znajdź kunia"; // tytuł, nazwa taska
        icon = "search"; // ikona, którą zobaczą na tasku gracze
        parentTask = "Soapy_Mission_XD"; // Task nadrzędny, odwołanie następuje po nazwie klasy
        conditionCodeShow = "true"; // Task będzie widoczny dla graczy na liście tasków
        conditionCodeSuccess = "unit1 distance horse < 50"; // Sukces taska nastąpi w momencie, kiedy dystans między obiektami unit1 oraz horse < 50
        onSuccessEvents[] = { "horseFound" }; // event wywoływany zaliczeniem taska (odwołanie nastąpi nieco niżej, czytajcie uważnie)
    };
    class KnockHorse { 
        title = "Zwal kunia"; 
        icon = "attack"; 
        object = "horse"; // Wskazuje nazwę konkretnego obiektu, który będzie posiadał na sobie powyższą ikonę
        parentTask = "FindHorse";

        conditionEventsShow[] = { "horseFound" }; // warunek, który musi być spełniony, by task się pojawił. Patrz linia 66
        conditionCodeSuccess = "!(alive horse)"; // by zaszło zwycięstwo obiekt "horse" ma być martwy (negacją jest znak "!")
        conditionCodeFailed = "!(alive unit1)"; // by zaszła porażka obiekt "unit1" ma być martwy

        onSuccessEvents[] = { "horseKnocked" };
        onFailedEvents[] = { "playerDied" }; // event wywołany porażką taska
    };
};
```

# Robienie misji 101

## **1. Ściągnij z kanału #presety_i_bzdety najnowszy preset**

Tak właściwie preset to jest po prostu misja ze skryptami. Wrzuć folder `preset.VR` z zipa do katalogu  `Documents\Arma 3 - Other Profiles\<nazwa_profilu>\mpmissions`. Odpal Armę, edytor a następnie otwórz ten preset.

_Jeżeli grasz na domyślnym profilu to ścieżka to `Documents\Arma 3\mpmissions`._

## **2. Zawartość presetu**

Preset (`preset.VR`) zawiera w sobie misję (czyli `mission.sqm`) oraz skrypty (wszystko inne).

Misja zawiera jednostki graczy z wpisanymi odpowiednimi skryptami i nazwami oraz moduły. Skrypty dodają obsługę pewnych funkcjonalności jak na przykład zmiana zasięgu widzenia.

Przygotowanie swojej misji, żeby była zgodna z presetem zamyka się w 2 krokach:

### Przygotuj kompozycje

Kompozycje to takie globalne szablony, gotowe grupy obiektów. Zaznacz same moduły, kliknij prawym na dowolny z nich i wybierz `Zapisz kompozycję niestandardową`. Ustaw jakąś nazwę i zapisz. Analogicznie dla reszty obiektów aż będziesz miał wszystkie poniższe kompozycje:

- Moduły **(!)**
- Gracze BLUFOR
- Gracze REDFOR
- Gracze INDFOR
- Skrzynie _(opcjonalne)_

Teraz w menu po prawej stronie możesz wybrać `Kompozycje (F2)` i na samym końcu po prawej `Niestandardowe`. Voila, już nigdy więcej nie będziesz musiał otwierać tej misji _(przynajmniej do czasu aktualizacji misji presetowej)_.

Otwórz swoją misję i ustaw potrzebne Ci kompozycje. Pamiętaj, że każda misja wymaga ustawienia kompozycji z modułami.

### Przekopiuj skrypty

Otwórz folder swojej misji (ponownie gdzieś w dokumentach) i przekopiuj do niego wszystkie **skrypty** z presetu. Uważaj, żeby nie skopiować `mission.sqm`, inaczej bezpowrotnie usuniesz swoją misję.

Najlepiej rozpocznij tworzenie misji od skopiowania skryptów, wtedy nawet jak coś nadpiszesz to nic nie stracisz, a masz już wszystko przygotwane.

## **3. Modlista**

Przygotowując misję, będziesz chciał (a w naszej grupie, nawet musiał) korzystać z modów. Najlepiej jakbyś od początku trzymał się jednej paczki modów.

Aby ustawić modlistę na misji, wystarczy że wybierzesz mody (lub skorzystasz z naszych gotowych modlist) i uruchomisz grę. Przy każdym kolejnym uruchomieniu Army pamiętaj żeby uruchamiać tę samą modlistę. W razie pomyłki edytor pokaże czego brakuje.

## **4. Ubierz lalki**

Masz już postawionych graczy, czas dostosować ich liczbę, ubranka i sprzęt.

### Liczba jednostek

Jeżeli brakuje Ci jednostek to skopiuj istniejące, gdy jest ich za dużo po prostu usuń. W przypadku dostawiania jednostek pamiętaj, że kolejność drużyn w lobby nie zależy od nazw tylko od kolejności ustawiania.

### Medykamenty

Pamiętaj, żeby każdy miał swój zestaw medykamentów. Przykładowy zestaw używany na misjach:

- 10 APAPów
- 10 bandaży uciskowych
- 10 bandaży elastycznych
- 1 adrenalina/epinefryna
- 1 morfina
- 2 stazy

### Radia

Są 3 główne modele radia, operujące na 2 różnych zakresach kanałów.

- Radio krótkie 343 - własny zakres kanałów
- Radio średnie 152 - zakres kanałów wspólny z 117F oraz z radiami w pojazdach
- Radio długie 117F - zakres kanałów wspólny z 152 oraz z radiami w pojazdach

W większości przypadków radia powinny być przydzielone w następujący sposób:

- **BPP** - krótkie
- **SL/TL** - krótkie + średnie
- **Zulu/HQ** - 2x średnie/długie
- **Wsparcie** - średnie/długie chyba, że ma pojazd z radiem

### Amunicja i broń

Dobór odpowiedniej ilości amunicji jest bardzo istotny. Nie ma jednej reguły co należy i ile tego dać. Poniższe liczby często przewijają się na naszych misjach i mogą jednak dać pogląd na sytuację:

- 6-7 magazynków 30-nabojowych
- 300-600 pocisków do KM
  - Im większy kaliber tym mniej pocisków się zmieści
  - Można rozważyć amunicyjnego żeby odciążyć kaemistę
- 1-2 granaty odłamkowe
- 0-2 granaty dymne
- 1-2 wyrzutnie jednorazowe (np. M136/RPG-26) na drużynę
- 0-1 dedykowanych wyrzutni AT/AA na drużynę
  - 2-3 pociski bez amunicyjnego
  - 3-5 pocisków z amunicyjnym

### Końcowe uwagi

- Staraj się, żeby gracze nie byli zbyt ciężcy.
  - Nie dawaj plecaków jeżeli nie jest to absolutnie konieczne dla danej roli.
  - Jedyne osoby, które mogą być w okolicach 30-35 kg to CKM i strzelcy AT/AA, ewentualnie amunicyjni.
  - Reszta powinna ważyć maksymalnie 25 kg.
- Jeżeli gracze mają pojazdy to można dać do nich dodatkową amunicję czy medykamenty, dzięki temu nie muszą oni tego ze sobą nosi i mogą być lżejsi.
- Można przygotować skrzynie ze sprzętem do zrzutu w razie potrzeby.

## **5. Przygotuj cele/zadania**

@3Mydlo3 przygotował takie sprytne coś do robienia misji i szkoda by było tego nie ogarnąć: <https://github.com/ArmaForces/Mods/tree/master/addons/tasks>

Jest tam opis tego jak z tego korzystać i jest to na tyle proste, że każdy ogarnie jak chwilę się nad tym zastanowi. W misji pokazowej przygotowałem 5, chyba najbardziej popularnych celów: wysadź cel, zbierz intel, znajdź cel, zabij cel, przejmij kontrolę na danym terenie. Można się tym posiłkować. Być może nie są to rozwiązania doskonałe, jednak na początek powinny wystarczyć.

W pliku `tasks.hpp` znajdują się krótkie komentarze pomagające się odnaleźć w tym co tam jest zrobione i jak to działa.

_Jeżeli zamierzasz bawić się skryptami to bardzo polecamy `Visual Studio Code` z dodatkami `SQFLint` od SkaceKachna oraz `SQF Language` od Armitxes. Możesz wtedy otworzyć w nim swój folder misji i pisać skrypty jak człowiek, oszczędzając sobie wiele nerwów._

## **6. Wstaw opisy**

W naszych misjach pojawiają się różne treści. Takie rzeczy można przygotowywać w pliku stringtable.xml. Misja pokazowa ma tam zdefiniowaną nazwę nazwę misji oraz treść intelu. Najprościej przyjąć, że to tablica stałych tekstowych.

## **7. Dodawanie akcji czy event handlerów**

Czasem możesz mieć potrzebę (nawet w prostej misji) zrobić coś więcej niż tylko chodzenie i zabijanie. Przykładem w misji pokazowej jest przeszukiwanie przedmiotu w celu znalezienia intelu - plik `initPlayerLocal.sqf`:

```sqf
// Dodanie akcji przeszukania i znalezienia intelu dla przedmiotu z nazwą "Intel1Item"
[
Intel1Item,
"Przeszukaj",
"\a3\ui_f\data\IGUI\Cfg\holdactions\holdAction_search_ca.paa",
"",
"_this distance _target < 3",
"_caller distance _target < 3",
{},
{},
{
    ["Intel1Found"] call CBA_fnc_serverEvent;
    player createDiaryRecord ["Diary", ["Intel", LLSTRING(IntelContent)]];
},
{},
[],
10,
0,
true,
false
] call BIS_fnc_holdActionAdd;
```

Dodatkowo w `initServer.sqf` znajduje się EventHandler kończący misję, który oczekuje na event `MissionEnd`:

```sqf
// Event kończący automatycznie misję. Można misję kończyć samemu komendą w konsoli
["MissionEnd", {
    titleText ["No i gitara", "PLAIN DOWN", 0.5];
    [{
        "EveryoneWon" call BIS_fnc_endMissionServer;
    }, [], 3] call CBA_fnc_waitAndExecute;
}] call CBA_fnc_addEventHandler;
```

Można wymusić dowolny event ręcznie dzięki poniższej komendzie w konsoli:

```sqf
["nazwa_eventu_który_zalicza_cel"] call CBA_fnc_serverEvent;
```

W tym przypadku wystarczy:

```sqf
["MissionEnd"] call CBA_fnc_serverEvent;
```

Dzięki temu w ostateczności (lub jeżeli cel jest zbyt trudny do automatycznego zaliczenia), można samemu zaliczyć zadanie wpisując stosowną komendę w konsoli:

```sqf
"EveryoneWon" call BIS_fnc_endMission;
```

Pamiętaj o tym żeby ją wywołać globalnie, a nie lokalnie, bo wtedy zakończysz misję tylko dla siebie, a reszta graczy pozostanie w grze. 

## **8. Ustawianie botów**

Do ustawienia botów wykorzystaj poradniki @Madin. Dobrą praktyką jest ustawianie 10-15 botów na gracza. Oczywiście liczba jest bardzo orientacyjna i zależy to od charakteru misji, jej długości, rodzaju uzbrojenia itd.

Pamiętaj tylko o tym, że Buildspawny mogą nie działać ze wszystkimi budynkami. Zdarza się tak, że działa np. jeden budynek na wioskę, co może na szybko powodować wrażenie, że działa a jednak nie działa. 

## **9. Importowanie ustawień do testów**

**Ten krok jest tylko dla zaawansowanych użytkowników chcących zmieniać ustawienia misji!**

Czasami możesz potrzebować przetestować ustawienia misji. Wchodzisz wtedy na <https://settings.armaforces.com/>, kopiujesz całą zawartość i w edytorze na górnej belce wchodzisz w `Ustawienia -> Ustawienia addonów` (``Settings -> Addon Options``) . Na górze wybierasz `Misja`, a następnie w prawym dolnym rogu klikasz `Import` i w okienku które się otworzyło wklejasz całą zawartość ww. strony. **Uważaj, żeby nie zaimportować tego do zakładki `Serwer`**, bo w edytorze to Ty jesteś serwerem i po prostu rozwali Ci Twoje ustawienia, czego nie da się cofnąć jeżeli miałeś coś poustawiane po swojemu.

## **10. Wgranie misji na serwer**

Jak będziesz miał gotową i przetestowaną misję zgłaszasz się do kogoś @ZOMO lub ewentualnie @BODE i oni już dalej Cię pokierują co, gdzie i jak wrzucić i jak to odpalić na naszej maszynie.

## **11. Testy na serwerze**

Następnie zadowolony odpalisz misję na serwerze i zobaczysz, że Twoje własne super skrypty nie działają, bo jeszcze nie wiesz co to lokalność. ( ͡° ͜ʖ ͡°)

## **Misja pokazowa**

[DO POBRANIA TUTAJ](/_data/guides/missionmaking/MisjaTutorial.zip)

Na potrzeby tego poradnika została przygotowana "misja", żeby bez nadmiaru informacji można było zapoznać się z częściami składowymi misji i pokazać że trzeba relatywnie niewiele aby misja była grywalna. Oczywiście, żeby to była dobra misja trzeba czegoś więcej niż kilku botów i zadań.

Głównym elementem misji są zadania. Kolejno są to:

- Znaleźć intel - akcja na leżaku obok respawnu
- Odnaleźć VIPa, zbliżając się do niego na mniej niż 100m
- Zabić VIP
- Wysadzić wieżę
- Przejąć kontrolę na zadanym terenie

Odkrycie zadania zabicia VIPa wymaga odkrycia najpierw jego pozycji poprzez odnalezienie Intelu. Następnie zbliżenie się, a ostatnim krokiem jest zabicie go. Kolejne etapy odkrywane są wraz z postępami graczy.

Przejęcie kontroli odbywa się w najprostszy sposób poprzez badanie przewagi na danym obszarze. Ma ono taki plus, że pojawienie się zaliczenia celu, może uśpić czujność graczy, bo zaliczenie tego celu nie znaczy, że wszyscy wrogowie nie żyją.

## **Pliki misji**

Nie wszystkie pliki z presetu zostały edytowane, gdyż nie było to niezbędne.

Wszystkie pliki `*.hpp` nie powinny być edytowane ani usuwane. Zwykłe usunięcie ich będzie powodowało crash army/serwera w momencie próby załadowania misji.

|     Plik/Folder      |                                                           Opis                                                           |
| :------------------: | :----------------------------------------------------------------------------------------------------------------------: |
|      functions       |                                             Pliki funkcji zawartych w misji                                              |
|         gui          |                         Pliki potrzebne do działania zmieniarki zasięgu widzenia i nazw drużyn.                          |
|   AF_funcions.hpp    |                                   Biblioteka funkcji zawartych w folderze `functions`.                                   |
|   description.ext    |                   Główny plik konfiguracyjny misji, raczej nie ma powodu, żeby tam cokolwiek edytować.                   |
|       init.sqf       | Skrypty wykonywane lokalnie na każdej maszynie w momencie jej dołączenia do misji (na serwerze w momencie startu misji). |
| initPlayerLocal.sqf  |    Skrypty wykonywane lokalnie u gracza gdy dołączy do misji. W misji pokazowej dodana akcja przeszukiwania obiektu.     |
|    initServer.sqf    |        Skrypty wykonywane na serwerze w momencie startu misji. W misji pokazowej dodany event zakończenia misji.         |
|     mission.sqm      |    Właściwy plik misji, tutaj zapisane jest wszystko co zrobisz w edytorze. Nie dotykaj go, bo zepsujesz sobie misję.    |
|  onPlayerKilled.sqf  |                                       Skrypt wykonywany w momencie śmierci gracza                                        |
| onPlayerRespawn.sqf  |                                       Skrypt wykonywany w momencie respawnu gracza                                       |
| script_component.hpp |                                           Nie dotykaj, bo zepsujesz wszystko.                                            |
|   stringtable.xml    |          Plik zmiennych tekstowych. W misji pokazowej zmieniona została nazwa misji i dodana zawartość intelu.           |
|      tasks.hpp       |                     Tutaj definiujesz wszystkie zadania. Omówione [TUTAJ](_5-Przygotuj-celezadania)                     |

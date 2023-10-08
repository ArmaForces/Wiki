# Od zera do missionmakera

Byśmy wszyscy robili misje niegorsze niż DDOS :)

## Wprowadzenie

Jest to poradnik mający na celu pokazanie jak zacząć przygody w tworzenie misji by nie ogłupieć.

W tym poradniku postaram się omówić:

- Co warto zaistalować, gdzie zaoglądać i czego się wystrzegać przy szukaniu "jak coś zrobić"
- Ogólny sposób używania edytora i co warto zrobić po pierwszym uruchomieniu
- Attributes, moduły które w edytorze są najcześciej wykorzystywane + triggerki + najprostrze wykorzystanie simple spawnów/build spawnów z MAI-a
- Wyjaśnienie presetu
- Co można robić by mieć jak największe szanse osiągnąc dobre fps-y.
- Wygląd kilku misji w edytorze. Co chciałem osiągnąc i co było skryptowane na misji.
- Na co zwracać uwagę w ogólnym tworzeniu misji, co pomaga, czego unikać i co zwykle nie ma sensu
- Ogólne Zeusowanie, problemy i rozwiązania
- Przykłady wątpliwych decyzji przy tworzeniu misji z wyjaśnieniem
- Wprowadzenie do pisania głupich skryptów w armie
- Czym jest lokalność i dlaczego jest to coś na co zawsze uważać
- Przykłady napisania skryptów z ogólnego "chce aby X się stało"
- Pisanie tasków
- Czego unikać przy skryptach, na moich błędach

Zaznaczm że nie jestem w to super dobry, poradnik zawierać będzie masę uproszczeń i niedopowiedzień które pewnie odkryjesz na własnej skórze. W takim wypadku serdecznie zapraszam do zwrócenia uwagi co dodać i poprawić.

## 1. **Co warto zaistalować, gdzie zaoglądać i czego się wystrzegać przy szukaniu "jak coś zrobić"**

Do zrobienia najbardziej generycznej misji byśmy wszyscy mogli zagrać wystarczy w sumie Arma + preset. [Preset](https://discord.com/channels/386882491484602368/541577429010087937) to gotowa misja która zawiera podstawową strukturę plików misji na której będziesz pracowować.

Wymienione dalej programy, linki i mody mogą w wielu przypadkach być niepotrzebne, jednak warto się z każdym zaznajomić by później wiedzieć szybciej gdzie sie udać

### **Ogólne strony www**

Przy tworzeniu misji spędzisz masę czasu na stronach typu:

- [Google](https://www.google.com/) - wyszukując czy ktoś gdzieś nie napisał jakiegoś prostego skryptu do tego czego szukasz. Wiele wyników odeśle cię do Forum Bohemi i Wiki Army
- [Wiki Army](https://community.bistudio.com/wiki/Category:Scripting_Commands) - Każdy skrypt który znajdziez na wujku google będzie składał się z komend które tutaj znajdziesz. Większość jest rozpisana co robi z podanymi przykładami jakiegoś zastosowania i uwagami społecznośći
- [Kanale "mission_making" na naszym discordzie](https://discord.com/channels/386882491484602368/590073885362487306) - Bardzo podobne zastosowanie co przy Googlu. Wpisujesz swoje pytania i ktoś kiedyś ci odpowie. Warto pytać jeśli wyniki w googlu nie są dla nas jednoznaczne, bądź mamy wątpliwości. Niezależnie czy to skrypty, zamysł czy możliwość osiągniecią czegoś
- [Wiki CBA](https://cbateam.github.io/CBA_A3/docs/index/General.html) - CBA zawiera kilka przydatnych rzeczy które są często wykorzystywane w podstawowych skryptach, omówione w sekcji poświęconej skryptom
- [ACE Functions Wiki](https://ace3.acemod.org/wiki/functions/) - ACE jest na zdecydowanej większości misji, dodaje wiele usprawnień jak i rzeczy których w podstawowej armie nie ma (Większość by denerwować Krystola). Zajrzysz tutaj choćby po to by zobaczyć co trzeba zrobić by uleczyć gracza skryptem na misji.
- Githubach/odpowiednikach - wiele rzeczy które się szuka ktoś już gdzieś kiedyś napisał i do czegoś użył. Zwykle na zasadzie pytasz o coś i dostajesz linka do funkcji/linijek kodu które robią to czego szukasz
- Skryptowe tutorialsy - [Multiplayer Scripting Bohemia](https://community.bistudio.com/wiki/Multiplayer_Scripting), [Ace Coding guide](https://ace3.acemod.org/wiki/development/coding-guidelines), [Acre Guideline](https://acre2.idi-systems.com/wiki/development/coding-guidelines-sqf)

### **Mody**

Przy tworzeniu misji w swojej modliście KONIECZNIE posiadać:

- [3denEnhanced](https://steamcommunity.com/workshop/filedetails/?id=623475643) - Dodaje gigantyczną liczbę rzeczy które przyspieszają, ułatwiają tworzenie misji
- [ZeusEnhanced](https://steamcommunity.com/workshop/filedetails/?id=1779063631) - Rozbudowanie i ułatwienie wielu rzeczy przy zeusowaniu
- [MAI-Dev](https://steamcommunity.com/sharedfiles/filedetails/?id=1852213757) - Simplespawny, BuildSpawny i Madinowe twory (które w większości są wyłączone na serwerze) przy odpowiednim stosowaniu bardzo optymalizujesz misje. Tak serio jest opcjonalny, jednak postaram się opisać jak z niego korzystać i rozwiązania jak bez niego również.

Opcjonalne, przydatne czasem rzeczy z workshopu:

- [Deformer](https://steamcommunity.com/sharedfiles/filedetails/?id=2822758266) - Możliwość edycji kształtu terenu w edytorze na potrzeby misji
- [ZEI-Zeus and Eden Interiors](https://steamcommunity.com/sharedfiles/filedetails/?id=1251859358) - dodaje moduł który zwyczajnie zapycha propami domki i podłogi/stoły
- [Emitter 3Ditor](https://steamcommunity.com/sharedfiles/filedetails/?id=1613905318) - Przydatne przy chęci dodania do swoich skryptów efektów cząsteczkowych (Bardzo zaawansowane)
- kompozycje budynków typu:
  - [ZEC - Zeus and Eden Templates / Building Compositions
](https://steamcommunity.com/sharedfiles/filedetails/?id=642912021)
  - [ZECCUP - Zeus and Eden Templates for CUP Terrains
](https://steamcommunity.com/sharedfiles/filedetails/?id=750186990)
- [O&T Expansion Eden
](https://steamcommunity.com/sharedfiles/filedetails/?id=1923321700) - Mod który dodaje vanillowe obiekty które normalnie nie są widoczne łatwo do postawienia przykładowo model pioruna, drzewa
- [Snapping for Eden and Zeus](https://steamcommunity.com/sharedfiles/filedetails/?id=2961167812) - Przydatne jak budujesz własne miasta, dużo płotów. obiekty starają się dopasować do obiektów wokół nich

UWAGA: Przy tworzeniu misji najlepiej nie używać tzw. modów opcjonalnych. JSRS zostawia ślad w pliku misji i później okazuje się że opcjonalny mod jest wymagany. Nie jest to coś co psuje totalnie misje, jednak dodaje to niepotrzebny krok by misje odpalić poprawnie na serwerze.

### **Programy**

Cała ta sekcja przy prostych misjach jest raczej super pomijalna, wszystko można napisać poprawnie  w edytorze Armowym i notatniku/Notepadzie++. Jednak na dłuższą męte i tak skończysz z czymś w rodzaju:

- [VisualStudio Code](https://code.visualstudio.com/) - Program do pisania kodu. Kiedy twoje skrypty zaczną być dłuższe niż 3 linijki to docenisz fakt że program będzie ci proponował komendy, kolorował czcionkę zależnie od typu danych, ukazywał gdzie kończy się twój nawias itd.

  - [SQF Language
](https://marketplace.visualstudio.com/items?itemName=Armitxes.sqf) - rozrzerzenie by nasz program wiedział co to SQF.
- Jakiś client FTP by wrzucać plik na serwer np. [WinSCP](https://winscp.net/eng/download.php)

### **Czego się wystrzegać przy szukaniu "jak coś zrobić"**

Długich skryptów. Bardzo rzadko to czego szukasz będzie wymagało długiego skryptu. Często zwyczajnie lepiej napisać na kanale do misji lub któregoś MM-a.

Często napotkasz skrypty które są częścią jakiś większych funkcji które mogą być do jakiegoś moda/systemu. W takim wypadku najlepiej postarać się znaleźć komendy które prawdodpobonie robią to czego szukasz.

Następnie sprawdź co ta komenda robi na Wiki Army3 i postaraj się ją sam użyć w sposób który spełni twoje oczekiwania.

Robiąc tak zdobywasz zwyczajnie doświadczenie co robi. Co by móc później robić bardziej skomplikowane rzeczy samemu.

Unikaj skryptów które mają w sobie wiele czegoś w stylu `_this select 0` <-- Powód prosty. Jeśli jest wiele razy to pewnie długi kod, a skoro długi i komuś nie chciało się zwyczajnie nazwać zmiennej w sposób który mówi co to. Będzie ci trudniej zrozumieć co to robi, ślepie kopiowanie kodu jest głupie.

## 2. **Ogólny sposób używania edytora i co warto zrobić po pierwszym uruchomieniu**

Po włączeniu edytora zobaczymy coś takiego

![CałyEdytor](../_data/guides/Editor/FullEditor.jpg)

Mimo że jest tu trochę rozwijanych menu które rozwijają się w kolejne opcje to pokaże tylko te rzeczy które są najbardziej używane

### Prawy przybornik

![prawy Przybornik](../_data/guides/Editor/PrawyPrzybornik.jpg)

- **F1** -> pojedyńcze jednostki podzielone na przypisanane im bazowo strony, cywile i obiekty

- **F2** -> Kompozycje, Tak samo jak wyżej. Dodatkowo jest jeszcze "CUSTOM" w którym znajdować się będą nasze zapisane kompozycje.

- **F3** ->  Triggerki

- **F4** -> Waypointy, aby jest móc postawić musisz mieć wybraną jakiegoś bota.

- **F5** -> Moduły (zębatka) w które stawiasz na mapie i one coś robią, czy to same czy po aktywacji z triggerem. Później wypisze te najcześciej stosowane. Są też Logic Entities ale z tego raczej nigdy nie skorzystasz. Opisane w dalszej części  

- **F6** -> Markery do stawiania na mapie

W wyszukiwarce na dole można wyszukać jakiś obiekt, kategorie, obiekty z moda (prefix moda można wybrać klikając strzałeczke po lewo)

### **Lewy Przybornik**

![Lewy Przybornik](../_data/guides/Editor/LewyPrzybornik.jpg)

Tutaj będą się pokazywać wszystkie stawiane przez nas obiekty.

Guzikami na dole można usunąć puste foldery jeśli jakieś dodaliśmy, ukryć, zrobić nowe, zablokować edycje czy widoczność obiektów w folderze.

### **Pasek u góry i Pasek narzędzi**

![Paski u góry](../_data/guides/Editor/Paski.jpg)

#### **Pasek u góry**

Pozwolę sobie opisać tylko rzeczy które mogą być mniej jasne po zajrzeniu w kategorie lub wymagające małej uwagi. W kolejności zaczynając od góry i czy jest coś tam wykorzystywane częściej. Dodatkowo czasem wypisze skróty klawiszowe

- **Scenario**
  - **Save/Open Mission** - Przy zapisywaniu misji **odznacz** opcje "**BINARIZE SCENARIO"** w celu łatwiejszej możliwości naprawiania potecjalnych problemów z załadowanymi modami po stworzeniu.
  - **MERGE** - łączy dwie misje w jedną jeśli są na tej samej mapie. Raczej przydatne jak ludzie robią wspólnie misje
- **Edit** - Tutaj w sumie się nie zagląda, znajduję się tutaj odpowiednik CTRL+Z/Y (cofnij zmiane/cofnij cofnięcie). Reszta rzeczy która się tutaj znajduję jest na drugim pasku narzędzi w jakieś formie.
- View
  - **Center on Selected entity (F)** - Przydatne jak mamy dużo obiektów i szukamy tego który wybraliśmy na lewym przyborniku
  - **Toggle Flashlight (L)** - Rozjaśnia mapę jeśli mamy ustawioną noc.
  - **Toggle Vision (N)** - Przełącza wizje między normalem/nokto/termo.
- Attributes
  - **General** - Znajdują się tutaj rzeczy które robi jeden plik z presetu, raczej nie trzeba tutaj absolutnie nic robić/zaglądać
  - **Environment** - Ustawienia pogody/mgły, nie ustawiać visualsettings to też jest w presecie. Wartości forecast to wartości pogody które są wartościami docelowymi które zachocą w ustawionym czasie
  - **Multiplayer** - Odpowiednik general pod multi, raczej się tutaj nie zmienia nic. Preset ustawia większość rzeczy które tutaj się znajdują
  - **Performance** - tutaj są ustawienia Bohemiovego Garbage collectora i ogólne ustawienia do Dynamicznej symulacji o której będzie dalej
- **Tools** - Tutaj się najwięcej zagląda bo są zwyczajnie pomocne, toolsy typu deformer też się tutaj pojawią.
  - **Debug Console (Ctrl+D)** - Otwiera konsole w której możesz pisać komendy, wklejać skrypty, śledzić jakieś wartośći u siebie/graczy/serwera
  - **Functions Viewer** - W grze/modach znajdują się masa funkcji które coś robią. Tutaj możesz sprawdzić co dokładnie
  - **Animations Viewer** - Można podejrzeć animacje.
  - **Camera/splendid camera** - Włącza tryb kamery by zrobić najlepsze zdjęcia w galaktyce.
  - **Field Manual** - Bohemiove poradniki + czasem mody tutaj coś dorzucają.
  - **Lobby Manager** - Ustawisz tutaj sloty w kolejności na misje.

  Tutaj zaczynaja się zbiory z większą ilością toolów/skryptów. Napisze tylko te które są warte używania z danych kategorii
  - **Utilities**
    - **3den Radio** - Zobaczysz dostępne pliki muzyczne, ich długość. Przydatne przy szukaniu classname potrzebnego do odpalenia muzyki skryptem
    - **Texture Finder** - Wyświetli ci wszystkie dostępne tekstury, ładuje się długo. Przydatne kiedy chcesz np. na białej tablicy ustawić teksture aktualnej mapy i potrzebujesz jej ścieżkę
  - **Placement Tools** - raczej nie użyjesz niczego tutaj, można postawić dane obiekty w kółka/siatki/linie
  - **Loadout Tools**
    - **Equipment storage editor** - alternatywa do wkładania przedmiotów w skrzynie/pojazdy. Czasem łatwiej dodać rzeczy przez to do jakiegoś pojazdu/skrzynki.
    - **Copy/Apply Loadouts (CTRL+Shift+C/A)** - Z tego bardzo często można korzystać przy ubieraniu graczy, kopiuje/wkleja całe EQ
    - **Remove NVGs** - Przydatne kiedy nastawiasz jednostki wyposażone domyślnie wyposażone w nokto. Zaznaszczasz wszystkie jednostki, klikasz i już jednostki są lżejsze o niepotrzebne nokto
  - **Vehicle customization** - nic tutaj nie jest przydatne praktycznie
  - **Debug Tools** - tutaj nic się nie przyda.
  - **Miscellaneous Tools**
    - **Toggle Simple object (ALT + S)** - Przełącza obiekt w Simple Obiekt
    - **Toggle Simulation (ALT + E)** - Wyłączą symulacje obiektowi
    - **... Dynamic Simulation (ALT + D)** - Obiekt ma zastosowaną Dynamiczną symulacje
    - **... Local Object (ALT + S)** - Obiekt nie jest sychronizowany po sieci
- **Settings**
  - **Preferences** - preferencja do edytora, polecam odnaczyc tutaj domyślne binaryzowanie nowych misji.
  - **Odpowiedniki** normalnych ustwaień army
  - **Addon Options** - tutaj ustawisz ustawienia modów.
- **Play**
  - **Play in multiplayer** - Przydatny przy sprawdzaniu samodzielnie czy twój skrypt który ma się odpalić jednemu graczu odpali się serio tylko jemu.
- **Help** - Każdy link tutaj to pomoc! Problem jest taki że czasem bardzo stara.

Reszta to zwykłe odnośniki do dokumentacji moda bądź naszego wiki

#### **Pasek Poniżej**

![Paski u góry](../_data/guides/Editor/Paski.jpg)

Zaczynając od lewej

- Nowy plik , otwórz plik, zapisz plik, opublikuj misje w steam
- Cofnij ostatnią czynność (UNDO) , Cofnij cofnięcie zmiany (REDO)
- Zwykły kursor, Przesuwanie, Obracanie, Skalowanie, Edytor Obszarowy
- Switch do widgetów który zmienia ich orientacje między obiektem i światem, włączenie przyciągania obiektów do ziemii, wlączenie przyciągania do powierzchni
- Przesuwanie o dany dystans, obracanie o dany kąt, trzecie to niby area scaling tylko nie wiem z czym to działa.
- ustawienia pogody(czemu to się nazywa intel?), wlączenie mapy, włączenie latarki, przełączenia trybu kamery
- Ostatnia rzecz nas nie interesuje, zawsze Scenario

### **Podsumowanie przydatnych skrótów klawiszowych**

    - Toggle Vision (N)
    - Center on Selected entity (F)
    - Toggle Flashlight (L)
    - Debug Console (Ctrl+D)
    - Toggle Simple object (ALT + S) 
    - Toggle Simulation (ALT + E) 
    - Toggle Dynamic Simulation (ALT + D)
    - Toggle Local Object (ALT + S) 
    - Copy/Apply Loadouts (CTRL + Shift + C / CTRL + Shift + A)
    - Undo/Redo (CTRL + Z / CTRL + Y)
    - Delete Selected (CTRL + X)

### **Podstawowe klikanie w edytorze i wigety**

Tutaj pozwolę sobie wstawić linki do poradników Bohemi które ładnie pokazują:

- [Pokaz wigetów](https://community.bistudio.com/wiki/Eden_Editor:_Transformation_Widget)
- [Podstawowe stawianie obiektów](https://community.bistudio.com/wiki/Eden_Editor:_Entity_Placing)
- [Łączenie jednostek w grupy/rozdzielanie](https://community.bistudio.com/wiki/Eden_Editor:_Connecting)
- [Przesuwanie/Podnoszenie/Obracanie obiektu](https://community.bistudio.com/wiki/Eden_Editor:_Entity_Transforming)
- [Edycja załogi pojazdu](https://community.bistudio.com/wiki/Eden_Editor:_Transforming_Crew)
- [Włączenie attributes obiektu](https://community.bistudio.com/wiki/Eden_Editor:_Entity_Attributes)
- [Zapisywanie własnej kompozycji (można tutaj poczytać o wszystkich atrybutach)](https://community.bistudio.com/wiki/Eden_Editor:_Setting_Attributes#Saving_Compositions)

W rzeczach wyżej nie jest pokazane jak sychronizować obiekt do modułu. Wygląda to podobnie jak grupowanie jednostek, należy:

- Na zaznaczonym obiektie/obiektach/module nacisnąć prawy myszy
- Wybrać connect
- Nacisnąć lewy myszy na module/trigerze/obiekcie z którym chcemy połączyć nasze coś

Dodatkowo mając zaznaczone jednostki i trzymając Shift można Prawym Myszy odrazu zrobić waypoint dla zaznaczonych jednostek w miejscu kliknięcia.

Podstawowe oznaczenia widoczne w edytorze jakie się widzi wyglądają tak

![Obrazek z czołgami w róznych stanach](../_data/guides/Editor/Oznaczenia.jpg)

Widoczne wyżej komentarze to prawy myszy w pustym miejscu i Place Comment

### **Co zrobić na początku**

- Ściągnij [Preset](https://discord.com/channels/386882491484602368/541577429010087937)
- Załaduj w edytorze misje która się tam znajduje. Trzeba ją wrzucić w folder z misjami typu C:\Users\Nazwa_użytkownika\Documents\Arma 3 - Other Profiles\Command%20DDOS\missions\ lub MPmissions
- Zaznacz wszystko przy komentarzu "Moduły"
- Zapisz jako Custom Composition. Nazwij jako moduły
- Możesz zrobić to samo z każdymi grupami jednostek jakie się tam znajdują
- Wywal z presetu plik mission.sqm i zachować sobie gdzieś taki folder

## 3. **Atrybuty, moduły które w edytorze są najcześciej wykorzystywane + triggerki + najprostrze wykorzystanie simpleSpawn/BuildSpawn/Reinforce z MAI-a**

Mogą paść tutaj pojęcia które zostaną wyjaśnione w dalszych częściach.

Każdy obiekt w Armie  posiada swoje Attributes w których można ustawić dość sporo rzeczy.

Zależnie od tego na czym odpalimy attrybuty bądź tego co będziemy mieli zaznaczone przy kliknięciu prawym myszy w celu odpalenia attrybutów dla kilku obiektów ujrzemy różne opcje w okienku. Należy czytać uważnie co się do czego odnosi

Każdy atrybut jest raczaj ładnie opisany po przytrzymaniu kursora nad nim.

Tutaj jednak wspomnę o initach oraz VariableName

Inity obiektów w dużym uproszczeniu to miejsce na kod którym sam obiekt jest dostępny pod zmienną `this`.

VariableName to po prostu nasza nazwa aby w jakimś skrypcie odnieść się do tego obiektu

### **Trigger**

Triggery które są widoczne w edytorze jako niebieskie flagi mogą tak naprawdę zrobić wszystko. Jednak preferowałbym je do używania prostych skryptów i prostych wykryć obecności jednostek. Bardzo często są sychronizowane z jakimiś modułami by te aktywowały się.

Triggerowe najważniejsze atrybuty to:

- **Type** - Praktycznie zawsze None
- **Activation** - Warunek triggera by ten był true. Najczęściej któraś strona bądź "AnyPlayer". Tutaj należy wiedzieć że działa to również jako "Co trigger będzie wykrywał" Anybody wykrywa każdy obiekt z możliwą fizyką (bez pocisków i wiekszości granatów)
- **Activation type** - najczęsciej Presesnt,Not Present
- **Repeatable** - Czy trigger ma mieć możliwość wywołania się ponownie.
- **ServerOnly** - Czy trigger ma być tylko na serwerze, w innym przypadku TRIGGER ISTNIEJE U KAŻDEGO w tym i serwera.
- **Condition** - Sprawdzany warunek, domyślnie jest tam `this`. W takim wypadku dla triggera ważny jest twój activation oraz activation type. Można tutaj wpisać dowolną rzecz która musi zwrócić true/false.
  - **Internal** - Jak często trigger sprawdza warunek. Nigdy 0.
- **On Activation** - Kod wywołany jak trigger spełni warunek. Warto dodać `deletevehicle thisTrigger;` na końcu jeśli jest to jakiś jednorazowy trigger
- **On Deactivation** - jak wyżej tylko jak warunek przestanie być spełniany.
- **Timer Type** - Coundown to opóźnienie po jakim czasie skrypt ma się wykonać od spełnienia warunku, a timeout to jak długo warunek musi być spełniany by trigger był trigger uznał go za spełniony.

### **Hide Terrain Objects**

Ukrywa obiekty mapy... Polecam je wrzucić w oddzielny folder w przyborniku i ukryć. Można edytować obszar i co ma ukrywać.

### **Edit Terrain Object**

Ten moduł powinien pozwolić ci zmieniać stan uszkodzeń budynków postawionych już na mapie, niestety jest popsuty. Najlepiej wykorzystać go do przypisania zmiennej obiektowi i dopiero wtedy zrobienia coś z nim w skryptach

### **Cover Map**

przyciemnia pozostał obszar mapy pokazując ładnie obszar misji.

### **Show / Hide**

Ten moduł jest przydatny jak chcesz optymalizować misje. Ukrywa/odkrywa jedostki/obiekty jednocześnie włącząjąc/wyłączając im symulacje. Mało kto go używa przez simplespawny.

### **Cała zakładka effects**

Są tutaj efekty i wezwanie CAS-a do jakiegoś triggerka.

### **SimpleSpawn**

SimpleSpawny w dużej mierze ułatwiają zachować ładne fps-y poprzez zrespienie botów połączonych z nim zołnierzy i pojazdów tylko w przypadku kiedy moduł zostanie aktywowany. Róznica między tym i SHOW/HIDE jest taka, że tutaj jednostki nie istnieją na mapie do czasu aktywacji. Moduł pobiera przypisane do jednostek Waypointy, stan grupy, formacje itd.

Posiada takie atrybuty jak:

- **Activation Distance** - jak blisko modułu musi pojawić się gracz.
- **Deactivation Distace** - jeśli ustawisz wartość dodatnią to zostanie do niej dodany Activation Distance. Jeśli gracze oddalą się od modułu o te wartość boty zostaną ponownie usunięte.
- **Plane/heli Activation** - Czy gracze w helkach/samolotach mogą odpalić moduł.
- **Spawn internal** - co ile zsychronizowane jednostki będą się respić po aktywacji modułu.
- **Spawn unit at once** - ile będzie ich respionych na każdy interwał.
- Delete Vehicles
- **Check Building** - jeśli jednostka była w budynku który został zniszczony to nie zrespi się.
- Activation Condition - warunek który musi zwrócić true by moduł się aktywował
- **Delete Trigger** - po 5 sekundach usunię trigger jeśli był jakiś z nim sychronizowany.
- **Force Activation** - Moduł się odpali jeśli którykolwiek warunek zwróci true (Distance, Activation Condition, połączony trigger).
- **code executed on ... spawn** - miejsce na skrypty które mają być wykonane na
  - unit
  - Group
  - Vehicle

### **BuildSpawn**

Podobne działanie co przy SimpleSpawn. Tylko tutaj jednostki respią się w budynkach na określonym przez nas obszarze. Łączymy jednostki z modułem.

Atrybuty :

- **Activation Distance**
- **Deactivation Distace**
- **Tickets** - ile botów może zrespić moduł
- **Minimal Distance** - Dystans po którym moduł uznaje że jakiś budynek wywalony z możliwości zrespenia w nim botów patrolowych i zostaną zrespione boty Stacjonarne.
- **Patrol Groups** - liczba grup patrolowych
- **Patrol Units** - liczba jedostek w jednej grupie patrolowej
- **Minimal Units** - Liczba żywych botów w grupie patrolowej aby ta została uznana za "wybitą"
- **Minimal Units Timeout** - po jakim czasie ma się coś zrespić pomimo faktu że grupy patrolowe nie są "wybite"
- **Limit per Building** - Ile razy Boty mogą wyjść z jednego budynku
- **Spawn Change** - szansa na zrespienie bota stacjonarnego w budynku do którego gracze podchodzą
- **Stationary Time** - jak długo bot stacjonarny nie może chodzić.
- **Bots per Building** - ile botów stacjonarnych ma być w środku
- **Limit Stationary** - ile może być botów wszystkich stacjonarnych
- **Defent Zone** - Funkcja które jest tutaj wymagana jest wyłaczona na serwerze.
- **Patrol Custom Spawn** - Po aktywacji modułu, pierwsze jednostki zrespią się w miejscu tych które są połączone z modułem
- **Include Not Supported** - Nie wszystkie budynki są wspierane, jeśli nię są to lepiej dać w nie obiekt o nazwie "AI Build Position"
- **Plane/Heli Activation**
- **code executed on ... spawn**
  - unit
  - Group
  - Vehicle

Jak bardzo ten moduł jest zajebisty na pierwszy rzut oka tak absolutnie proszę nie przesadzać w poleganiu na nim. Głównie dlatego że rozleniwia i na dłuższą mete boty wybiegające z każdego budynku też nie są zawsze zbyt fajne.

### Civilians

Respi cywilów z jednostek zdefiniowanych lub tych które połaczysz. Chodzą, boją się strzałów.

Atrybuty raczej są jasne i dość podobne do poprzednich wymienionych

### Reinforce

Moduł którego zadaniem jest sprawić że do danego miejsca przyjechało wsparcie, wyładowało się i ruszyło na pozycje modułu. Sychronizujesz z pojazdem który znajduję sie w miejscu z którego ma przyjechać.

Nie wspiera latadeł. Łączysz z pojazdem z piechotą i elo. Strzelające pojazdy domyślnie respią się bez ammunicji.
Strzelające pojazdy potrafią dostać wylewu.

Atrybuty są bardzo podobne do poprzednich:

- **Get Out Distance** - Dystans od modułu, w którym nasze wsparcie ma wysiąść i ruszać z buta.
- **Number of Vehicles** - ile razy połączony pojazd razy ma przyjechać
- **minimal crew** - ile musi zostać ekipy z pojazdu by mógł przyjechać następny
- **Despawn** - Pojazd po desancie wsparcia będzie starał się wrócic do punktu startu i zniknąć.
- **Spawn Internal**
- **Max Number of units on map**
- **Activation condition**
- **code executed on ... spawn**
  - **vehicle**
  - **unit**
  - **Patrol Group**
  - **Group Vehicle**

### Przykłady użycia simplespawnów/buildspawnów/reinforce

![Wiocha z modułami](../_data/guides/Editor/Wiocha.jpg)

Ogólny przebieg tego tworu jest taki:

Gracze aktywując pierwszy simplespawn zrespią jednostki na dachach oraz obwodzie wiochy.

W simpleSpawnie  w kodzie wywoływanym na każdej jednostce znajduję się

```sqf
params ["_unit"];
_unit setUnitPos "UP";
_unit disableAI "PATH";
```

[params](https://community.bistudio.com/wiki/params)
[setUnitPos](https://community.bistudio.com/wiki/setUnitPos)
[disableAI](https://community.bistudio.com/wiki/disableAI)

Kod ten uniemożliwia zrespionym botom z modułu poruszanie się i nakazuje im stać.

BuildSpawn ma mniejszy zasięg niż simplespawn. Boty powinny zacząć wychodzić z budynków przy trochę bliższym dystansie graczy od zabudowań. Na tyle dużym by nie widzieli respiących się botów w budynkach.

Kolejny simplespawn respi jednostki wewnątrz wiochy w kilku miejscach za małymi trenchami. Posiada ten sam kod co wyżej.

Po wejściu gracza w trigger w wiosce powinno przyjechać wsparcie które wyładuje się i ruszy wspomóc boty w wiosce.

### **Obrzydliwe, nie chce korzystać z Mai-a jakie są alternatywy**

Dla osiągnięcia podobnych efektów:

- Jednostkom widocznym z daleka trzeba wyklikać wyłączenie pathu w atrybutach/wrzucić im w init `this disableAI "PATH"; this setunitpos "UP"`/
- Ukryć je przez moduł SHOW/HIDE, dodać triggery które je odkryją.
- Musiałbym ręcznie stawiać boty w budynkach. poustawiać im jakieś waypointy.
- Wsparcie musiałoby by być również aktywowane przez moduł SHOW/HIDE.

Czy warto? Szczerze uważam że na dłuższą męte byłoby to strasznie męczace. W teorii można tutaj użyć symulacji dynamicznej tylko trzeba mieć na uwadze jakie ustawienia się ustawi. Tylko dalej masz tutaj istniejącą jednostkę, którą serwer musi sprawdzać.

W wielu scenariuszach dość dużo jednostek respi się z palca i jest to jak najbardziej ok, Zwłaszcza kiedy:

- Przebieg misji jest bardzo trudny do określenia
- Ustawienie jednostek w sensowny sposób i złączenie je z modułami byłoby zbyt pracochłonne i groziło jakimiś probletami typu, że gracze podchodzą od dupy strony i widzą jak boty się respią
- Misja nie będzie miała dużo jednostek strzelających jednocześnie.
- Reagujemy na działania graczy w formie jakiegoś wsparcia wroga.

## Co można robić by mieć jak największe szanse osiągnąc dobre fps-y

- Redukować liczbę aktywnie strzelających botów. 50 aktywnie biorących udział botów w walce z graczami może osiągnąć zadowolający efekt strzelania się. Jak masz dużo aktywnych botów (X > 100) to warto się zastanwoić czy serio te wszystkie boty muszą być aktywne w takich liczbach.
- Starać się nie postawić za dużo obiektów na metr kwadratowy. Tym którym można to wyłączyć symulacje/zrobić je lokalnymi/ zrobić je jako simpleobject.
- Fajnie by najwięcej Botów było jednak zrespionych po stronie serwera. Jeśli reśpisz Bota z zeusa, ten bot jest liczony przez twój komputer.
- Starać się nie używać skryptów z nieskończonymi pętlami które często coś sprawdzają/robią
- Symulacja dynamiczna na skrzynkach graczy i ich pojazdach to całkiem ok pomysł.
- Usuwanie trupów, botów i zniszczonych pojazdów z wcześniejszych części misji.

O czym warto pamiętać:

- Długie rozpatrywanie jak zoptymalizować misje nie ma sensu.
- Dynamiczna symulacja na wrogich pojazdach latających to zły pomysł. Lepiej wyłączyć symulacje i włączyć ją nawet z zeusa

## **Wyjaśnienie presetu**

Wcześniej trzeba było skopiować sobie preset, wyciągnąć z niego moduły i przygotować sobie pliki by później je zwyczajnie wrzucać do naszego folderu misji. Pytanie więc po co to?

Moduły które masz w kompozycji to tak naprawdę:

- Miejsca dla headlessa - Wszyscy wiemy że arma jest bardzo jednowątkowa w wydajności i liczy się jaki masz takt na pojedyńczym rdrzeniu, a nie ile ich masz. Serwer cierpi trochę na to samo. Więc wymyślili że można podłączyć drugi raz serwer jako oddzielną instacje i przerzucić na nią obliczenia AI/skrypty tak aby serwer skupił się na jak najlepszym wysyłaniem nam informacji.

 W praktyce więcej z tym pierdolenia niż aktualnego zysku więc jest to wyłączone. Niemniej wspominam bo jest w modułach.
 Jest też moduł który rozdziela właśnie AI po podłączonych Headlessach. Można włączyć jednym prostym klikiem w ustawieniach addonów. Jednak czemu nie warto będzie w sekcji o lokalnośći.

- Punkt Respawnu gdzie gracz pojawi się po respie lub reconnect.
- Moduł zeusa.

Żołnierze których kopiowałeś mają w initach grup kod na zmiane ich nazw w rozgrywce. Zeusowe sloty mają wyłączony damage. Ich plusem jest to że są vanillowi, nie mają na sobie jakiś dziwnych skryptów które potrafią mieć niektóre mody z jednostkami.

A pliki?

|     Plik/Folder      |                                                           Opis                                                           |
| :------------------: | :----------------------------------------------------------------------------------------------------------------------: |
|      functions       | Pliki funkcji zawartych w misji, jakbyś pisał własne skrypty zrób nowy folder i tam je wrzucaj|
|         gui          | Pliki potrzebne do działania zmieniarki zasięgu widzenia i nazw drużyn. Raczej nie zaglądaj|
|   AF_funcions.hpp    | Czarnia magia, tutaj nic nie zmieniaj.|
|   description.ext    | Główny plik konfiguracyjny misji. Będziesz tutaj zaglądać by dodać pliki własne pliki muzyczne, dodać banner [Link](https://community.bistudio.com/wiki/Description.ext)|
|       init.sqf       | Skrypty wykonywane lokalnie na każdej maszynie w momencie jej dołączenia do misji (na serwerze w momencie startu misji).|
| initPlayerLocal.sqf  | Skrypty wykonywane lokalnie u gracza gdy dołączy do misji.|
|    initServer.sqf    | Skrypty wykonywane na serwerze w momencie startu misji. W misji pokazowej dodany event zakończenia misji.|
|     mission.sqm      | Właściwy plik misji, tutaj zapisane jest wszystko co zrobisz w edytorze. Nie dotykaj go, bo zepsujesz sobie misję.|
|  onPlayerKilled.sqf  | Skrypty wykonywane w momencie śmierci gracza |
| onPlayerRespawn.sqf  | Skrypty wykonywane w momencie respawnu gracza|
| script_component.hpp | Czarnia magia, tutaj nic nie zmieniaj.|
|   stringtable.xml    | Plik w którym są zmienne tekstowe, główne zastosowanie przy tym jak chciałbys zrobić misje która zawiera teskty tasków/skryptów powiązanane z tym jaki ktoś ma ustawiony język gry.|
|      tasks.hpp       |  Plik z Taskami do misji na bazie  [link](https://github.com/ArmaForces/Mods/tree/master/addons/tasks)|

## Wygląd kilku misji w edytorze. Co chciałem osiągnąc i co było skryptowane na misji

Uprzedzam to co tutaj zobaczysz nie jest/było idealne. Należy patrzeć na to wszystko przez pryzmat tego że każdy ma swoją wizje i tego że ja serio nie jestem w to jakoś dobry.

Niemniej liczę że pokazanie tych potworków komuś pomoże. Będzie wiele coś o skryptach bez tłumaczenia o co chodzi. Później coś o nich będzie dokładniej.

Na pierwszy ogień idzie misja o jakże nie ładnej nazwie

### "Nocna prosta misja"

![Nocna Misja](../_data/guides/Editor/NocnaMisja1.jpg)
![Nocna Misja](../_data/guides/Editor/NocnaMisja2.jpg)
![Nocna Misja](../_data/guides/Editor/NocnaMisja3.jpg)

Ogólne założenie:

- Stworzyć krótką misje wymagającą początkowej komunikacji między dwoma oddziałami. W celu określenia jak chcą osiągnąc cel.
- Celem dla graczy było zniszczenie obrony przeciwlotniczej znajdującej się na wyspie. 3 Bardelasy i 2 stanowika AA. Wyplenienie wyspy z wszystkich przeciwników było drugoplanowe.
- Po zniszczeniu AA miało przylecieć wsparcie ogniowe w postaci dwóch śmigłowców bojowych.
- Gracze mieli mieć możliwość przemieszczenia się łódkami jakby chcieli.

Skrypty na misji i wykorzystane rzeczy:

- Skrypt który sprawdzał ile jest botów w gigantycznym trigerze by zaliczyć task z oczyczczeniem wyspy z piechoty. Obrzydliwą pętlą.
- Proste sprawdzanie czy bardelasy/stanowiska AA zostały zniszczone, każde miało własnego taska.
- Task był tak napisany że sobie patrzyłem czy gracze oznaczyli pozycje bardelasów/AA. Jeśli oznaczyli to odpalałem skrypt by pojawił im się task dedykowany zniszczeniu tego co oznaczyli.
- Bałwanki dawały małą wiadomość graczowi po podejściu.
- włączenie latarek botom, wyłączenie chodzenia wybranym i ustawione ambient animacji w atrybutach niektórych botów
- SimpleSpawny <-- nie powinno ich być.
- Hide terrain object - Bo w bunkrze był krzak.

Co trochę nie wyszło:

- Dałem za mało magów, fartem magi przeciwników pasowały do broni graczy.
- Poczułem jak bardzo zmuszenie bota który walczy do zrobienia czegoś jest trudne, zwłaszcza jak to pojazd.
- Bot więzień zmienił lokalność na headlessa i miał wyjebane w inita by nie chodził.

Poświęcony czas na zrobienie misji:

- Edytor jakaś godzina
- Skrypty nie pamiętam, ale długo bo to był czas kiedy "Boże jak mam zaliczyć taska skryptem, jak to sprawdzić..."

### Operacja Banan

![Operacja Banan](../_data/guides/Editor/OperacjaBanan1.jpg)
![Operacja Banan](../_data/guides/Editor/OperacjaBanan2.jpg)
![Operacja Banan](../_data/guides/Editor/OperacjaBanan3.jpg)
![Operacja Banan](../_data/guides/Editor/OperacjaBanan4.jpg)
![Operacja Banan](../_data/guides/Editor/OperacjaBanan5.jpg)
![Operacja Banan](../_data/guides/Editor/OperacjaBanan6.jpg)
![Operacja Banan](../_data/guides/Editor/OperacjaBanan7.jpg)

Ogólne założenie:

- Misja na większą liczbę osób czołg i bradleye. Strzelanie, umocnione pozycje wroga.
- W tle wątek że tutaj coś badano i w niektórych miejscach są odpady radioaktywne które są niebezpieczne dla graczy. W sumie miałbyć wątek paranormalny kiedyś.
- Miało być trochę notek które opowiadały o badaniach i tym że ludność tam jest niezadowolona i wręcz czeka na możliwość wsparcia wypchania rosjan z regionu (mieli przyjść jako wsparcie)

Skrypty na misji i wykorzystane rzeczy:

- Masa simplespawnów,buildspawnów i reinforce.
- Ukrywajki terenu by postawić kilka rzeczy.
- [BIS_fnc_initInspectable](https://community.bistudio.com/wiki/BIS_fnc_initInspectable) dla notek na laptopach czy dokumentów.
- Skrypt znaleziony na necie który blurował graczom obraz jak stali przy skażonych miejscach, a jak stali za długo to zgon. Dzięki pomocy naszych doświadczonych członków dodano tutaj możliwość wejścia w taki obszar z wymaganym sprzętem by gracza nie zabiło.

Co nie wyszło:

- Ustawiłem za dużo ticketów w buildspawnach, było ich dużo. Każdy mógł zrespić 20 botów.
- Za duże zrobiłem, misja się rozbiła na drugą część.
- Ośrodek zamordował fps-y.
- Headlessowe zmiany lokalności sprawiły że coś co nie miało biegać, biegało.
- Wiele obiektów nie powinno mieć włączonej symulacji, aktualnie wiele z tych obiektów byłoby też lokalne.
- Pojazdy wroga zrespione simplami dostały wylewu.

To była moja 3 misja? wiedza skryptowa absolutnie zerowa.

Poświecony czas:

- Jeden dzień edytor.
- Godziny spędzone na pytaniach jak coś działa i czytanie komend skryptów by zrozumieć co robią.

### Leśne dziady

![Leśne Dziady](../_data/guides/Editor/LesneDziady1.jpg)
![Leśne Dziady](../_data/guides/Editor/LesneDziady2.jpg)
![Leśne Dziady](../_data/guides/Editor/LesneDziady3.jpg)
![Leśne Dziady](../_data/guides/Editor/LesneDziady4.jpg)
![Leśne Dziady](../_data/guides/Editor/LesneDziady5.jpg)

Ogólne założenie:

- Gracze prowadzą działania ofensywne mające na celu zniszczenie umocnionych miejsc, obrony przeciwlotniczej czy wrogich magazynów.
- Na mapie znajdują się pola minowe których położenie jest raczej nieznane.
- Wrogowie są rozsiani po całym obrzasze działań.
- Podczas misji czasem jakiś gracz miał doznać anomali/zwidów.
- Gracze mieli mieć drona do zwiadu.

Skrypty na misji i wykorzystane rzeczy:

- Simplespawny, masa triggerów i gamelogic w których zwyczajnie było dodanie widocznego na zeusie markera gdzie miałem informacje który event zrobić by zaliczyć taska.
- Dzięki pomocy skrypt który sprawiał że dla kogoś jest noc, a dla innych nie
- Bałwiany labirynt kooperacyjny o którym zapomniałem. Gracz w labiryncie nie widział bałwanków. Wejście w bałwanka wywalało go z labiryntu. Musiał być prowadzony przez kogoś z zewnątrz. Zbierało się drewienko.
- Dziwnie i obrzydliwie wykorzystany [BIS_fnc_holdActionAdd](https://community.bistudio.com/wiki/BIS_fnc_holdActionAdd) na laptopie który miał symulować przeszukiwanie plików na laptopie, zwyczajnie można było znaleźć intel w różnym czasie. koniec końców go tam nie było.

Co nie wyszło:

- Trochę nie dokończyłem kilku rzeczy, miałem dodać kilka notek w obozach wrogów czy intel na laptopie. Bałwiany labirynt i rozkmina jak puścić raz muzykę z laptopa zjadła za dużo czasu.
- Zapomniałem że gracz który widzi zwidy pewnie strzeli do tego co widzi. Na dzień dzisiejszy dodałbym prosty skrypt który po strzale wychodzi z tych zwidów. Koniec konców te zwidy do niczego nie prowadziły.
- Trochę za mało informacji dałem graczom gdzie warto się udać.

Czas robienia:

- edytor - 1 dzień
- skrypty do samego końca, dopiero w dzień misji odkryłem jak zrobić by muzyka raz się odpaliła. Na dzień dzisiejszy mojej wiedzy rozwiązanie było do dupy jak większość skryptów tam. Jednak działały.

### DDOS

![DDOS](../_data/guides/Editor/DDOS1.jpg)
![DDOS](../_data/guides/Editor/DDOS2.jpg)
![DDOS](../_data/guides/Editor/DDOS3.jpg)
![DDOS](../_data/guides/Editor/DDOS4.jpg)
![DDOS](../_data/guides/Editor/DDOS5.jpg)
![DDOS](../_data/guides/Editor/DDOS6.jpg)

Ogólne założenie:

- Zrobić misje w której gracze mają czuć że oddanie strzału to ostateczność.
- Dodać element gdzie gracze wiedzą co robią siły na wyspie.
- Przygotować wpierdol graczom, trase ucieczki od niej. Nakładając na nich presje na każdym kroku.

Przebieg misji bo jest absolutnie bardzo fabularyzowany.

Wyspa jest chroniona przez system komputerowy który zarządza ruchami jednostek. Zadaniem graczy jest dostanie się do dwóch serwerów owego systemu i ściągniecie danych.

System przeżywa poteżną awarie która doprowadziła do tego że gracze dotarli w obszar misji.

Gracze mieli jak najszybciej:

- Dezaktywować systemy obrony przeciwlotniczej w regionie by umożliwić sobie ewakuacje.
- Dotrzeć do serwerów, pobrać ich dane i wrócić do punktu startu.

Do ich dyspozycji był wgląd do tego co owy system zarządza. Z każdą chwilą system odzyskiwał coraz większą sprawność. Im wpadka była późniejsza tym moja reakcja miała być bardziej stanowcza.

Widoczne triggery w wiekszości odpowiadały za odpalenie jakiegoś zdarzenia które zostawiało ślad w tym co graczą mogą przeczytać w logach systemu. Przykładowo było to wyruszenie śmigłowa szturmowego na patrol, przejazd kolumny czołgów. Czy przylot helikoptera transportowego po piechotę w okolicy.

To co chciałem by było najlepszym elementem to moment kiedy system zrzuca jednostki specjalne. One miały zawsze spaść pytanie brzmiało tylko czy będzie to z winy graczy czy przygotowanego zwrotu akcji.

W najlepszych przypadku gracze mieli wyłączyć systemy obrony AA, ukraść dane i wrócić do punktu startowego jak gdyby nigdy nic.

Podczas przylotu ich transportu system miał się aktywować i je zestrzelić. Tutaj gracze mieli zostać skierowani do przebicia się do bazy na mniejszej wyspie by ukryć się przed zagrożeniem (Miało to być komunikowane przez system który "Obliczał ich szanse na ucieczkę po zrobieniu czegoś"). Po dopłynieciu na wyspe mieli mieć chyba 3 minuty na dotarcie im system strzelił Laserem śmierci w celu zniszczenia wejścia do podziemi. Misja miała się zakończyć po dotarciu do końcowych wielki wrót i wyjścia mecha

**Skrypty na misji i wykorzystane rzeczy:**

- Masa trigerów które odpowiadały za odpalenie mini zdarzeń i wyświetlenie logów w systemie.
- Możliwość by nie puszczała się muzyka w skryptowych miejscach.
- Dużo uszkadzania światełek by te symulowały migotanie świateł w tunelach.
- Dodanie własnych źródeł światła dla lepszego klimatu.
- Timer który pokazywał jak długo czekać pobranie na plików.

Co nie wyszło?

- Gracz wlazł we wrogi obóz i to już było zwyczajnie ciężko zignorować.
- Cały misterny plan nie ujrzał swiatła dziennego bo umarli.

Czas przygotowania:

- 2 miesiące. Większość tego czasu to tak naprawdę testowanie czy moje przygotowane gówno skrypty zadziałają, czy mogą się odpalić w złej kolejności.

Na dzień dzisiejszy skrypty w tej misji są absolutnie obrzydliwe, praktycznie każdą rzecz trzeba by przepisać na nowo bo nie nadają się do ponowego użycia gdziekolwiek. Pokazuje ona jednak że przy byciu zapartym można osiągnąc naprawdę fajne rzeczy, nawet jeśli nie potrafi się wiele :)

### Dionizos

![Dionizos](../_data/guides/Editor/Dionizos1.jpg)
![Dionizos](../_data/guides/Editor/Dionizos2.jpg)

Założenie:

- Krótka misja w której gracze wcielają się w oddział który ma udać się na miejsce w którym doszło do strzelaliny między terrorystami.
- Ich zadaniem jest zlikwidać terrorystów, uwolnić cywili i rozbroić miny które zostały podłożone.
- Odkryć czemu terroryści się tam zaczęli strzelać.
- Zwrot akcji polegający na tym że gracze znajdują urządzenie które grozi ekplozją i trzeba je zresetować. Po restarcie urządzenie zabiera graczom noktowizje,radia, psuje wszystkie pojazdy i wyłączą elektryczność w okolicy.

**Skrypty na misji i wykorzystane rzeczy:**

- Urządzenie robi boom EMP i czyśći mapę z elektroniki za wyjątkiem jednej skrzyni do której gracze mogli wrzucić ograniczoną ilość swojego sprzętu i desantuje CSAT-owych viperów.
- SimpleSpawny
- 3 [BIS_fnc_initInspectable](https://community.bistudio.com/wiki/BIS_fnc_initInspectable) które miały wskazywać że jest urządzenie i że trzeba schować rzeczy do tej skrzynki.

Co nie wyszło:

- Gracze znaleźli tylko jedną notkę, a te którą myślałem że na 100 % znajdą to nie.
- Wywołanie efektu pioruna przypadkiem używało złego wyzwolenia efektu przez co zamiast piorun raz uderzyć w miejscu zesłania vipera to uderzył tyle razy ilu było graczy.

Czas przygotowania:

- Edytor - 1 godzina
- Skrypty - 1 godzina, większość wykorzystałem zmienione rzeczy z swoich poprzednich misji.

### Po co to wszystko pokazuje

Głównie po to aby pokazać że błędy na misjach zawsze będą (każda ma jakieś błędy, jedne nie wpływają na ogólny przebieg misje inne mogą już niestety bardziej).

 Pokazać że nawet niewiele umiejąc można zrobić naprawdę skomplikowane misje przy wytrwałości. Ja serio niewiele potrafiłem przy robieniu tej misji z kradnięciem danych z serwerów i dalej nie umiem super dużo.

Ukazać że krótkie/proste misje są też spoko. Misja z zniszczeniem AA na wyspie trwała może 1h, Można by wywalić tam wszystkie skrypty. wywalić simplespawny i zwyczajnie dokładniej powiedzieć o misji na jej starcie.

Ostatnia misja trochę pokazuje w sumie taką małą ewolucje tego że im więcej się potrafi tym zwyczajnie mniej rzeczy się robi w edytorze. Skrypty w niej są lepszej jakości niż w misji o kradnięciu danych i widać to tym że większość skryptów wisi w plikach, a nie w initach obiektów/triggerach.

Nie jest to absolutnie pokazanie że misje mają tak wyglądać. Widzieliśmy wiele misji niektóre były w całości misje robione przez opcje w zeusie, a ich odbiór był lepszy niż moich misji czy innych super skryptowanych misji.

O czym to świadczy? Od dobrej misji nie wymaga się super skryptów, zajebiste rozbudowania czy by jej przebieg był super oskryptowany/przygotowany, czy były napisane najlepiej jak się da (ale warto próbować bo później łatwiej się korzysta w przyszłości ze swoich skrypcików).

Misja powinna spełniać najważniejszy warunek "być taką że sam byś chciał zagrać". Jako gracz wiesz co potrafiło być meczące, co było spoko itd.

## Na co zwracać uwagę w ogólnym tworzeniu misji, co pomaga, czego unikać i co zwykle nie ma sensu

Ogólne pomocne porady które zwykle potrafią pomóc dostrzec problemy założeń naszej misji, czy przyspieszyć jej powstawanie.

- Stawiaj sobie komentarze na mapie co gdzie chcesz by było/jest. Misje czasami robi się kilka w krótszych sesjach i zwyczajnie łatwiej zapobiec w ten sposób ciągłym zmianom kiedy wcześniej się określi co gdzie ma być. Dodatkowo osobie sprawdzającej misje łatwiej zrozumieć będzie przebieg misji jeśli dużo się postawiło.
- Ubierać graczy na końcu. Ubierasz graczy często to tego co spotka ich na misje, jak zrobisz to na początku istnieje szansa że i tak będziesz coś poprawiał. Ubieranie graczy trwa zajebiście długo.
Z własnego doświadczenia powiem że szybkim sposobem ubierania graczy jest wejście w ich arsenał -> wywalenie wszystkiego co mają w ubraniu, dodanie tam medykamentów i radia -> wejście w kamizelke oczyszczenie ją z granatów, dodanie magów bo pewnie były w ubraniu.
- Pytać o pomoc jak coś zrobić, absolutnie za dużo czasu na początku się traci na rzeczy bo nie wiemy jak je osiągnąć.
- Nie słuchać ślepo poradników, wiele rzeczy na które zwracają uwage nie mają aż tak wielkiego znaczenia. Ten też traktuj krytycznie i podchodź do niego z dozą że informacje tutaj nie muszą być zawsze dobre.
- Nie robić pierwszych misji zbyt wielkich czy skomplikowanych. Dobrze zrobione proste rzeczy również dają satysfakcje
- Pamiętać że gracze wiedzą tylko to co im powiesz. Robisz jakieś dziwne rzeczy czy masz jakiś narzucony plan to lepiej kogoś/jakoś na niego nakierować.
- Podchodzić krytycznie do opinii/krytki graczy. Czasem to na co narzekają nie jest aż takim dużym problemem, nawet jeśli długo się o tym mówi. Przykładowo Mydło narzekał na dużą liczbę medykamentów dość długo. A to raczej problem niewielki bo gracz może je wyrzucić, jednak pamiętać zawsze o opiniach graczy warto.
- Szukaj najprostrzych rozwiązań swoich problemów, staraj się wykorzystywać rzeczy które wiesz jak działają. Jak nie wiesz pytaj i pytaj o tłumaczenie. Czytaj wiki komend.
- Testuj skrypty dzień przed misją.
- Nie bój się mordować graczy jak grają gówno.
- Nie przesadzaj z liczbą grenadierów, posiadają losową możliwość zabicia wszystkich (jak zaczną napierdalać z granatnika to często są w tym bardzo skuteczni)
- Nie dawaj helek czy pojazdów tylko po to by przewiozły na początku graczy. Po co?
- Zapierdalanie pół mapy gdzie nic się nie dzieje przez 25 minut nie jest fajne.
- Jeśli są pojazdy dla graczy to zastanowić się nad tym co się stanie jak gracze je stracą i czy nie zdominują rozgrywki.

## Ogólne Zeusowanie, problemy i rozwiązania

## Przykłady wątpliwych decyzji przy tworzeniu misji z wyjaśnieniem

## Wprowadzenie do pisania głupich skryptów w armie

Ta część jest w sumie najważniejsza, a zarazem natrudniejsza do wytłumaczenia. Bo wszędzie pada coś o skryptach, lokalnośći, różnych plikach i zwyczajnie ciężko ogarnąc od czego zacząć. Postaram się jednak wyjaśnić jak najlepiej to co potrafię :>

Uproszczeń będzie masa, niedopowiedzeń jeszcze więcej.

Do pisania skryptów w armie używany jest  SQF (Status Quo Function)

[Bohemiove wprowadzenie do SQF](https://community.bistudio.com/wiki/Introduction_to_Arma_Scripting)

Pisząc skrypty będziesz używał [zmiennych](https://community.bistudio.com/wiki/Variables), [funkcji](https://community.bistudio.com/wiki/Function) i [komend](https://community.bistudio.com/wiki/Category:Scripting_Commands).

`Zmienne` mogą być `Globalne` i `Lokalne`

```sqf
ZmiennaGlobalna = 0;
Private _ZmiennaLokalna = 1;
```

`Zmienne` mogą być przypisane do wszyskiego i w każdej chwili mogą zmienić swoją wartość i typ.

[Magiczne Zmienne](https://community.bistudio.com/wiki/Magic_Variables) są to zmienne dostępne w róznych miejsach dla wygody np. `this` lub `ThisList` w triggerach

[Typy Danych](https://community.bistudio.com/wiki/Category:Data_Types)

```sqf
// to jest komentarz
Zmienna1 = player; // komenda która zwraca jednostke gracza, Obiekt
Zmienna2 = 1; //  Liczba
Zmienna3 = [1,2,3]; // tablica z liczbami
Zmienna4 = "Masz piękne Oczy"; // Tekst
Zmienna5 = True; // Boolean
Zmienan6 = {Player setdamage 1}; // Kod
Zmienna7 = Zmienna5; // Inna zmienna w tym wypadku to dostanie wartość True
Zmienna8 = 5 + 3; // liczba powstała w wyniku dodawania
zmienna9 = Call Function_roll; // Wywołanie funkcji która zwróci jakąś wartość
Zmienna10 = Alive player; //zwróci true albo false. Zależy czy gracz żyje
```

Będziesz używał masy Bracketów (nie wiem jak to przetłumaczyć)

`[]` - `tablice` (Array) w których będziesz miał `zmienne`. Masa komend zwraca zmienne w postaci tablicy, kolejna masa potrzebuje kilku wartości by wykonać swoje działanie.

```sqf
 Helka = createVehicle ["ah1w", position player, [], 0, "FLY"];
 ```

`()` - Będziesz tego używał by poprawić głównie czytelność swojego kodu i zmiennić kolejność wykonywania działań.

```sqf
private _desiredTerrainHeight = (getPosWorld _Crater select 2) - (random 0.50 + 0.25); 
```

`{}` - Używane przy typie zmiennych typu `code`, przykład w komendzie [AddAction](https://community.bistudio.com/wiki/addAction)

```sqf
this addAction
[
	"title",	// title
	{
		params ["_target", "_caller", "_actionId", "_arguments"]; // script
	},
	nil,		// arguments
	1.5,		// priority
	true,		// showWindow
	true,		// hideOnUse
	"",			// shortcut
	"true",		// condition
	50,			// radius
	false,		// unconscious
	"",			// selection
	""			// memoryPoint
];
```

[Funkcje](https://community.bistudio.com/wiki/Function) służą do wywoływania przypisanych do nich skryptów. Często przyjmują dane wejściowe i mogą zwrócić nam dane wyjściowe. użwamy by nie wklejać gigantycznych ścian kodu za każdym razem. W dużym uproszczeniu `Zmienna globalna` z `kodem` który możemy uzyć

```sqf
TAG_fnc_showHint =
{
	hint "Function was executed!"; // Function will show a hint when executed
};
call TAG_fnc_showHint;
```

### Scheduler, kod zaplanowany i ten niezaplanowany (scheduled, unscheduled)
W Armie funkocjunje coś takiego jak [Scheduler](https://community.bistudio.com/wiki/Scheduler#Scheduled_Environment). Jest coś w rodzaju Nadzorcy skryptów któremu podajemy skrypty, a on je wykonuje.

Jego głównym zadaniem jest kolejkowanie skryptów przy okazji starać się sprawić by było nam jak najtrudniej popsuć armę skryptami.

Wprowadzana on coś takiego jak środowiska w którym nasz kod jest wykonywany jest to `Scheduled` i `Unscheduled`.

Pozwolę sobie wkleić gdzie jest kod `Scheduled`:

- `init.sqf`
- `initServer.sqf`
- `initPlayerLocal.sqf`
- `initPlayerServer.sqf`
- functions with postInit attribute (although suspension is allowed, any long term suspension will halt the mission loading until suspension has finished)
- code executed with `spawn`
- code executed with `execVM`
- code executed with `exec`
- code executed with `call` from a scheduled environment

`Unscheduled`:

- `Debug Console`
- `Triggers`
- `Waypoints` (condition and activation)
- All pre-init code executions including functions with preInit attribute
- FSM conditions
- Event Handlers on units and in GUI
- EachFrame code (Event Handler / Scripted EH / onEachFrame)
- Object initialisation fields <- Czyli nasz inity obiektów w edytorze
- Expressions of Eden Editor entity/mission attributes
- Code execution with call from an unscheduled environment
- Code executed with `remoteExecCall`
- Code inside isNil
- SQF code called from SQS code
- Conversation Event Handler
- Code inside collect3DENHistory

Czym się te dwa łepki róznią? W `Scheduled` masz gwarancje że kod tam wpisany będzie w takiej samej kolejności jakiej go napisałeś, przy `Unscheduled` istnieje szansa kolejność się zmieni.
Kod scheduled ma ogranieczenie jak długo możesz być wykonywane i są to 3ms na kazdą klatkę.

Kolejną ważną rzeczą jest fakt że bez środowika `Scheduled` nie użyjesz `Sleep` czyli zwyczajnego uśpienia skryptu na jakieś sekundy.

Jednak tutaj odrazu powiem że przy pomocy `Spawn` tworzymy środowiko `Scheduled`

```sqf
[] spawn {
    systemchat "Za 5 sekund zostaniesz uleczony";
    sleep 5; 
    player setdamage 0;
};
```
### SQF Syntax

Najlepiej zajrzeć sobie tutaj i poczytać [Armowe Wiki](https://community.bistudio.com/wiki/Category:Syntax)

Przykłady z czego się czesto korzysta

[IF](https://community.bistudio.com/wiki/if)

```sqf
if (alive player) then {
    systemchat "Ty żyjesz"; // true
} else { // Przy If część od else jest OPCJONALNA
    systemchat "Nie żyjesz" // false
};

if (alive player) then {
    player setpos (getpos teleport);
};

if (player distance Vip > 100) exitwith {
    systemchat "Jesteś dalej niż 100 metrów od Vipa!";
};

FajnaZmienna = false;

//Wykrzynik sprawia że kod tutaj się wywoła bo teraz sprawdzamy czy jest FajnaZmienna ma wartość False

if !(FajnaZmienna) then { 
    Systemchat "False";
};

// Dwa warunki muszą tutaj być true

if ((alive player) and (player distance Vip > 100)) then {
        systemchat "Jesteś żywy i dalej niż 100 metrów od Vipa!";
};

// tutaj jeden

if ((alive player) or (player distance Vip > 100)) then {
        systemchat "Jesteś żywy lub dalej niż 100 metrów od Vipa!";
}; 

```

[For](https://community.bistudio.com/wiki/for)
```sqf
for "_i" from 0 to 3 do {
    systemchat _i;
};
```

[ForEach](https://community.bistudio.com/wiki/forEach)
```sqf
{_x setdamage 1} foreach allplayers;
```
[Switch](https://community.bistudio.com/wiki/switch)

```sqf
switch (floor random 5) do
{
	case 1: { hint "one"; };
	case 2: { hint "two"; };
	default { hint "zero, three or four" };
};
```

## Czym jest lokalność i dlaczego jest to coś na co zawsze uważać

## Przykłady napisania skryptów z ogólnego "chce aby X się stało". Pomocne rzeczy CBA i jego fajne komendy

## Pisanie tasków

## Czego unikać przy skryptach, na moich błędach
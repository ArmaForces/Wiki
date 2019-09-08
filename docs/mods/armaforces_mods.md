
# ArmaForces - Mods

Mod oferuje zbiór przydatnych funkcjonalności dostosowanych pod rozgrywki prowadzone przez ArmaForces. Jest on rozbity na wiele modułów aby uprościć rozwój addona.

# Main

Moduł głowny, jest wymagany przez wszystkie inne moduły i zawiera ogólne funkcjonalności nie pasujące do reszty modułów.

### Keybindy

- **"Tryb zrzutu ekranu"** - Umożliwia ukrycie całego interfejsu użytkownika. Domyślnie nie przypisany.

### Ustawienia Addonów

- **RHS - Skrypt na opóźnione uruchamianie pojazdów** - Umożliwia wyłączenie/włącznie skryptu na opóźnione uruchamianie silnika w RHS. Domyślnie włączone.

# ACE Explosives

### Keybindy

- **Zdetonuj wszystkie ładunki** - Umożliwia detonacje wszystkich ładunków połączonych z aktualnie posiadanymi zapalnikami. Domyślnie nie przypisane.
- **Wysadź się** - Powoduje detonacje wszystkich ładunków przypisanych do "Czuwaka". Domyślnie nie przypisane.

### Ustawienia Addonów

- **Opóźnienie detonacji** - Czas przez jaki trzeba przytrzymać przycisk detonacji aby zdetonować ładunki.

# Curator

Usprawnienia dla modułu Zeusa:
- Kontrolka z ilością graczy oraz AI pod lewym panelem
- Zmiana logo Zeusa na nasze własne

# Diagnostics

Funkcje diagnostyczne/administracyjne:
- **Options > FPS List** - Lista z aktualnymi FPS wszystkich graczy na serwerze
- **Options > DLC List** - Lista z posiadanymi DLC wszystkich graczy na serwerze
- **Markery diagnostyczne** - Markery znajdujące się poniżej lewego dolnegu rogu mapy. Zawierają informacje o FPS oraz ilości lokalnych grup Serwera oraz HC

### Ustawienia Addonów

- **Diagnostyka** - Umożliwia włączenie/wyłącznie markerów diagnostycznych. Domyślnie włączone.

# Difficulty

Powoduje że domyślnym poziomem trudności jest "Własny"

# Faces

Odblokowuje w profilu i arsenale cześć twarzy które są domyślnie zablokowane.

# Flag

### Obiekty
- **Flaga ArmaForces** - Flaga z naszym logo
- **Flaga GSC** - Flaga _"Generycznego Gówno Państwa"_
- **Flaga Afrene** - Flaga państwa Afrene, Isla Duala
- **Flaga Molatia** - Flaga państwa Molatia, Isla Duala

### Przyczepianie flag

Funkcjonalność przyczepiania flag do pojazdów lądowych oraz statków. Pozwala na przyczepienie flag do pojazdów za pomocą menu interakcji ACE aby umożliwić łatwiejszą identyfikację na polu walki. Przydatne w przypadku przejmowania pojadów przeciwnika.

!> Duża ilość flag może negatywnie wpłynąć na wydajność. Zalecanie jest nie przesadzanie z ilością oznaczonych pojazdów

[Filmik pokazowy funkcjonalnośći](https://www.youtube.com/watch?v=vBnpNlwuk38)

Dostępne flagi:
- Flaga strony gracza
- ArmaForces
- Czerwona
- Zielona
- Niebieska
- Flaga medyczna
- _Bez flagi_

### Ustawienia Addonów
- **Ranga potrzebna do przyczepiania flag** - Ranga jaką musi mieć gracz aby móć przyczepiać flagi. Domyślnie sierżant

# FRIES

Powoduje dodawanie Fast Rope Insertion Extraction System _(Fries)_ do wszystkich kompatybilnych śmigłowców.

### Ustawienia Addonów

- **Automatyczne dodawanie FRIES** - Umożliwia włączenie/wyłącznie automatycznego dodawania FRIES. Domyślnie włączone.

# Goggles

Dodaje efekty okularów ACE do różnych gogli. Na ten moment wsparcie tylko i wyłącnie dla opasek na oczy z Contact DLC.

# Insignia

Dodaje insygnia na mundurach graczy mające na celu ułatwić identyfikację drużyn. Dowódcy drużyn mają możliwość wybrania insygnia swojej drużyny z menu zarządzania drużyną w menu interakcji ACE. 

Moduł daje możliwość ustawienia insygniów drużyny lub indywidualnej jednostki z poziomu edytora misji. Aby to zrobić należy otworzyć panel atrybutów grupy/jednostki.

[Atrybuty grupy](_data/af_mods_insignia_group.png)

[Atrybuty jednostki](_data/af_mods_insignia_unit.png)

Jeżeli jednostka ma przydzielone indywidualne insygnia to może wybrać je z menu zarządzania drużyną w menu interakcji ACE. W takim przypadku indywidualne insygnia mają priorytet nad insygniami drużynowymi.

[Wybieranie insygniów przez ACE menu](_data/af_mods_insignia_ace_selection.png)

### Ustawienia Addonów

- **Ranga potrzebna do ustawiania insygnia swojej drużyny** - domyślnie Sierżant
- **Ranga potrzebna do przydzielania inysgniów innym drużynom** - domyślnie Porucznik

# Ladder_tweaks

Nieznacznie przyspiesza poruszanie się po drabinach.

# Loading

Dodaje nasz "branding" na ekranie ładowania.

# Map

Moduł dodaje różne użyteczne funkcjonalności związane z mapami. Takie jak możliwość rozkładania mapy, dodawnie intela do statycznych map oraz dodawanie tymczasowej mapy na ekranie briefingu.

### Ustawienia Addonów

- **Mapa na ekranie briefingu** - Czy pokazywać mapę na ekranie briefingu nawet gdy gracz nie posiada mapy w ekwipunku. Domyślnie włączone.

## Rozkładane mapy

Gdy gracz posiada mapę ma on możliwość rozłożenia jej na ziemi jako obiekt widoczny dla wszystkich graczy. Rozłożona mapa posiada punkt interakcji ACE dzięki któremu osoby nie posiadające mapy w swoim ekwipunku mogą z niej skorzystać. Szczególnie przydatne w sytuacjach gdy tylko jedna osoba w drużynie posiada mapę (np. WW2, Wietnam).

Oprócz map papierowych istnieje również możliwość podglądu map ściennych lub na statywach.

[Prezentacja funkcjonalności](https://www.youtube.com/watch?v=Hou4YLOMNHY)

## Mapy z "Intelem"

Funkcjonalność pozwala dodać do map ściennych oraz na statywach markery które będą widoczne tylko gdy gracz "otworzy" dany konkretny obiekt do którego zostały przypisane markery. Pozwala to na wykorzystanie map jako istotnego elementu misji zawierającego waże informacje.

### Dodawanie markerów do obiektu mapy

1. Utwórz markery
2. Zaznacz markery które chcesz dodać do mapy
3. `PPM` > `Log` > `Skopiuj dane markerów` (powinien wyskoczyć komunikat o skopiowaniu danych)
4. Usuń zaznaczone markery
5. Otwórz atrybuty obiektu mapy
6. Wklej zawartość schowka nadpisując zawartość pola "Dane markerów"

[Wideo poradnik](https://www.youtube.com/watch?v=s-mOQ2FblzE)

# Med_strecher

Dodaje obiekt "Bardzo wygodne nosze", są to zmodyfikowane nosze które po chwili od położenia się na nich leczą w pełni gracza. Jako że pozycja leżąca w noszach jest normalnym stanowiskiem "pojazdu" to można ładować do nich nieprzytomnych graczy.

Czas do wyleczenia wynosi 30 sekund i nie jest konfigurowalny na ten moment.

# Safestart 

Moduł bezpiecznego startu, powoduje opusczenie oraz zablokowanie karabinu przy rozpoczęciu rozgrywki. Dodatkowo moduł ostrzega jednorazowo jeżeli gracz ma zbindowny rzut granatem pod "G".

### Ustawienia Addonów

- **Zaczynaj z zabezpieczoną bronią** - Czy zabezpieczać broń przy starcie rozgrywki, nienadpisywalne przez serwer. Domyślnie włączone.

Nie ma możliwośći wyłącznie automatycznego opuszczania broni.

# Settings

Moduł powstał jako obejście ograniczenia nie pozwalającego zmieniać ustawień z zakładki serwer gdy korzysta się z ustawień CBA poprzez `userconfig\cba_settings.sqf`. Zamiast tego można korzystać ustawień w pliku `userconfig\custom_cba_settings.sqf` (taki sam format pliku), w przypadku korzystania z ustawień w tym pliku są one ustawiane w preInit. 

Zastosowanie takiego rozwiązania ma jedną zasadniczą wadę, nie pozwala ono na ustawianie wartości ustawień dodawanych przez misję gdyż nie istnieją one jeszcze w tym momencie. Aby rozwiązać ten problem postwała jeszcze inna funkcjonalność...

Plik z ustawieniami do usunięcia `userconfig\custom_cba_settings_delete.sqf`, ma taki sam format jak poprzednie pliki aczkolwiek wartości ustawień w tym pliku nie mają znaczenia. Jakiekolwiek ustawienia znajdujące się w tym pliku są usuwane z pliku profilu serwera. Usuwanie następuje poza API CBA co umożliwa na zresetowanie zapisanych wartości dla ustawień dodawanych przez misję.

# Slingload

Moduł ma na celu rozwiązanie problemu z odczepiającym się ładunkiem na linach gdy występuje desync. Powoduje on przeniesienie lokalności ładunku do pilota śmigłowca który go podnosi.

Ze względu jak działa lokalność w armie funkcjonalność nie działa na obiekty które mają załogę.

# Spotlight

Usuwa z menu głównego domyślne "kafle" z trybami gry/kampaniami i zastępuje je jednym który pozwala na dołączenie do naszego serwera.

# Sturdy_aircraft

Moduł zwiększa odporność śmigłowców oraz samolotów na obrażenia HE oraz uderzenia. Daje to większą szanse na udane lądowanie awaryjne.

# Vehicles

Zawiera nasze własne modyfikacje pozazdów.

### Pojazdy
- **Dmuchana łódź** - Ponton który można spakować do 2 plecaków (łódź + silnik)

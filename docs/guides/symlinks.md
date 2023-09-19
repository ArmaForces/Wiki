# Symlinki

## Wstęp

Poradnik został opracowany z myślą o graczach, którzy chcieliby zaoszczędzić precjozo jakim jest wolna przestrzeń na ich dyskach SSD, ale wciąż posiadać Armę na swoim szybszym dysku. Pokazuje on jak osiągnąć zamierzony cel przerzucając często spore paczki modów na dysk HDD i tworząc do nich linki. Twórcą poradnika jest @Renchon. 

  [Symlink - ArmA SSD, mody HDD](https://drive.google.com/file/d/1lWbsHtAd6JXc7X-ZiMUpWLUAMQwwKrw9/view)


Simlink 101 dla ludzi, którzy kończyli podstawówkę, nie informatykę - czyli jak
mieć mody z Army 3 na HDD gdy gra jest na SSD.

Dysk C – SSD | Dysk D – HDD

Wyłączamy Steam!
Następnie dysku HDD tworzymy foldery (dwa, ponieważ download i content), w którym
chcielibyśmy mieć mody do naszej ukochanej gry Army 3. Dla uproszczenia ja mam po
prostu nazwane foldery i ścieżkę tak samo jak w oryginalnym katalogu steam.
Pamiętaj, że ostatni folder 107410 nie może mieć zmienionej nazwy!

![image](https://github.com/ArmaForces/Wiki/assets/55647626/463a7613-b981-4431-823c-f1ac40235544)
![image](https://github.com/ArmaForces/Wiki/assets/55647626/91d7d3c3-c752-4077-ba26-7f939e30c9e4)

W każdym z folderów 107410 w katalogu content i downloads tworzymy puste pliki tekstowe z
losową nazwą (dla sprawdzenia czy całość działa)

![image](https://github.com/ArmaForces/Wiki/assets/55647626/c8c9b80a-dc9d-4a98-9805-db1c2852fd02)

Posiadając już zrobiony katalog na dysku HDD, przystępujemy do skopiowania adresu folderów z
dysku SSD i HDD

![image](https://github.com/ArmaForces/Wiki/assets/55647626/7fb16832-045e-4ad8-9826-23d405734111)

Dokonujemy tego odpowiednio dla ścieżek SSD downloads/107410 ; content/107410 i vice-versa dla
HDD
Ostatecznie nasze ścieżki powinny wyglądać tak jak poniżej: (Oczywiście trzeba pamiętać o różnicy w
nazwaniu folderów.

C:\Program Files (x86)\Steam\steamapps\workshop\content\107410
C:\Program Files (x86)\Steam\steamapps\workshop\downloads\107410

D:\workshop\content\107410
D:\workshop\downloads\107410

Następnie wyszukujemy programu Windows PowerShell i przytrzymując Shift + Ctrl klikamy na niego
Enter – To powinno odpalić go w trybie administracyjnym. [Musi być odpalony z prawami
administratora]

![image](https://github.com/ArmaForces/Wiki/assets/55647626/07b887dd-d765-4fb2-b50d-60d028b0d310)

New-Item -ItemType SymbolicLink -Path "Link" -Target "Target"
Jest komendą używaną do simlinku – w miejscu Link (pomiędzy znakami cudzysłowia)
dajemy ścieżkę do dysku SSD a w miejscu Target to SSD. Oznacza to, że na dysku SSD tworzy się
<mydło zredaguj xD> którego celem jest dysk HDD.
W przypadku moich wyżej podanych ścieżek komenda będzie wyglądała tak:

New-Item -ItemType SymbolicLink -Path "C:\Program Files
(x86)\Steam\steamapps\workshop\content\107410" -Target
"D:\workshop\content\107410"

New-Item -ItemType SymbolicLink -Path "C:\Program Files
(x86)\Steam\steamapps\workshop\downloads\107410" -Target
"D:\workshop\download\107410"

Podajemy komendę i ją wykonujemy, powinno wyskoczyć nam coś takiego dla obydwu.

![image](https://github.com/ArmaForces/Wiki/assets/55647626/ab1e3c27-48a3-4ef0-89da-c1d01f442d4a)

A same foldery (już w ścieżce SSD) powinny wyglądać tak (czyli mieć ikonkę skrótu):

![image](https://github.com/ArmaForces/Wiki/assets/55647626/69d8928a-b2ec-4a32-9bcf-2971b27d9983)

Gdy wejdziemy akurat w ten folder, to powinniśmy zobaczyć znajome pliki

![image](https://github.com/ArmaForces/Wiki/assets/55647626/13b41423-eeb8-43fe-8444-e173f2422800)

Podobnie powinien wyglądać folder w katalogu downloads

Możemy teraz włączyć Steam i zacząć pobierać mody

Troubleshooting [Na tą chwilę problemy z którymi się spotkałem]
1. Wyskakuje mi komenda, że się nie da bo coś źle
Trzeba sprawdzić czy ścieżka katalogu jest prawidłowa

2. Jak klikam enter to komenda się nie wykonuje
Kliknij LPM na koniec komendy, aby znaczek od pisania był na końcu, jak
jest gdzieś indziej to komenda może się nie wykonywać (sam się na tym
naciąłem)

3. Folder pozostaje taki sam, nic się nie zmienia
Można spróbować wyjebać folder 107410 (downloads i content) z SSD i
wykonać komendę - nie trzeba zmieniać jej treści

4. Jak mi się mody ściągają to folder 107410 na SSD zamienia się z
powrotem w zwykły w katalogu downloads.
Wyjebać wszystko co w środku, wyłączyć steama! jeszcze raz i
simlinkować ponownie

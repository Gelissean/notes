- mapovacia funkcia kľúča z veľkého rozsahu na menší
- vznikajú kolízie
- rýchly výpočet, rovnomerná distribúcia kľúčov do celej tabuľky

hešovacie funkcie:
- priame hešovanie
- modulo delenie - m je prvočíslo
- mid-square - prehodnotenie stredných hodnôt
- skladanie - rozdelenie čísla na niekoľko podčísel a prehodnotenie
- výber číslic
- polynomiálne adresovanie
- ascii hodnota textového kľúča
- suma ascii hodnôt znakov

riešenie kolízií:
1. otvorené adresovanie - následovné voľné miesto za obsadeným
	- linear probing - následovný voľný znak
	- quadratic probing - vzniká sekundárne zhlukovanie
	- random probing - kľúč násadou generátora
	- dvojite hešovanie
2. zreťazenie - vytvorením zoznamov na mieste
	- separate chaining
	- overflow area - vyhradená oblasť pre kolidujúce prvky
3. košíky - každá pozícia má niekoľko prvkov
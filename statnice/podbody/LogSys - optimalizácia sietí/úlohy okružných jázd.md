možné deliť podľa:
- čas uspokojovania požiadavkov
	- čas je pevne určený (rozvrhovacia úloha)
	- čas je daný časovým intervalom
	- čas nie je určený (prepravná úloha)
- počet stredísk
	- jedno
	- viac
- poloha požiadavkov v sieti
	- v uzloch (rozvoz)
	- na úsekoch (kropenie ulíc)
	- v uzloch aj úsekoch (zalievanie zelene)
- typ dopravnej siete:
	- neorientovaná
	- orientovaná
	- zmiešaná
- maximálna doba prejdenia trasy
	- rovnaká pre všetky vozidlá (homogénny park)
	- každé vozidlo má inú dobu
	- nie je zadaná
- operácia prevádzaná u zákazníka
	- nakládka
	- vykládka
	- obe
- kritérium kvality riešenia
	- minimálne náklady
	- minimálny počet trás
	- zmiešané kritérium
	- minimaxové kritérium
***
**Metódy riešenia**
- Metódy primárneho zhlukovania (cluster first - route second)
	1. zanedbajú sa podmienky trasy, rieši sa zhlukovanie zákazníkov do zhluku, aby bolo každého možné obslúžiť jednou cestou
	2. riešenie úlohy obchodného cestujúceho
- metóda primárneho trasovania (route first - cluster second)
	1. zanedbáva sa kapacita, rieši sa úloha obchodného cestujúceho
	2. získanú trasu upravíme tak, aby vznikli okružné jazdy rešpektujúce kapacity
- metódy výhodnostných koeficientov a vsúvania
	- v duálnom prípade sa buduje trasa vsúvaním zákazníkov do neprípustnej trasy, spájanie viacerých okružných jázd
	- v primárnej verzií sa zlepšujú trasy operáciou s najväčšou možnou úsporou
	- **Clarke-Wright**ova metóda
![[clarke-wright.png]]
- výmenné metódy
- metódy využívajúce matematické programovanie
	- dekompozičné heuristiky![[dekompozicne heuristiky.png]]
- interaktívne metódy
	- možnosť zásahu užívateľa
- presné metódy
	- princíp vetiev a hraníc/rezov

uzavrený Eulerovský ťah
- existuje ak do každého vrcholu vchádza práve toľko hrán, koľko z neho vychádza
- prejsť všetky hrany jedným ťahom
- algoritmus:
	0. inicializácia - každému uzlu priradíme počet nespracovaných úsekov
	1. predhoc od súčasného uzla - ak je počet nespracovaných úsekov nenulový, pridajme k ťahu jeden z nepoužitých a opakuj krok 1, inak krok 2
	2. zmena súčasného začiatku a konca ťahu - ak platí, že všetky hrany sú spracované končíme, inak reorganizujeme uzavretý ťah tak, aby začínal a končil v inom uzle

[[Úloha čínskeho poštára]]

**Dvojfázová sekvenčná heuristika**
**Lin-Kernighan**
1. určenie jazdy vozidiel aby uspojovali všetky požiadavky zákazníkov
2. postupné zmenšovanie dĺžky trás / počtu vozidiel výmenou reťazcov zákazníkov
Skladá sa z štyroch pravidiel:
1. počiatočné úseky sú vylúčené z procesu výmeny
2. úseky, ktoré boli do procesu vsunuté už nebudú vylúčené
3. rozbíjanie podcyklov
4. úspora $G$ nesmie klesnúť do záporných hodnôt
Generuje sa strom preskúmaných sledov
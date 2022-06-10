**Huffmanovo kódovanie**
- čím je znak frekventovanejší, tým kratšia bude sekvencia bitov v jeho kóde
- riziko správne dekódovať text
![[huffman.png]]
- niekoľko spôsobov kódovania
	- 2-fázové Huffmanovo kódovanie
		- zistenie frekvencií
		- kódovanie
		- časovo náročné
	- Statické Huffmanovo kódovanie
		- jeden kódovací strom pre všetky príbuzné texty
	- Adaptívne Huffmanovo kódovanie
		- začať s prázdnym stromom
		- po prečítaní každého znaku upraviť strom tak, aby bol optimálny

***
**Kódovanie Shannon-Fano**
- dvojprechodové kódovanie:
	1. usporiadanie symbolov podľa početnosti
	2. rozdelenie symbolov na 2 časti aby suma výskytov sa vľavo čo najviac rovnala tej sume v pravo, ľavej časti priradíme 0, pravej 1
	3. cyklicky oprakujeme delenie kým nezískame unikátne časti
***
**LZ78**
- počas kompresie sa tvoria dvojice <pozícia, rozširujúci bajt>
![[LZ78_1.png]]
![[LZ78_2.png]]
***
**Lempel-Ziv-Welch**
- kóduje sekvenciu znakov
- všetky kódy majú rovnakú bitovú dĺžku
- jedno-priechodový typ kódovania
- pri veľkosti 12 bitov je veľkosť slovníka $2^{12} = 4096$ sekvencií
- algoritmus, ktorý obsahuje automatický návrh a prispôsobenie heuristickej metódy

**Metóda Supra**
- má k dispozícií metódu (heuristiku alebo metaheuristiku) $Metoda(u,x')$, ktorá na základe parametrov $u$ a vstupného riešenia $x'$ vydá výstupné riešenie $x$ s účelovou funkciou $q$
- pomocou metódy definujeme funkciu $f(u) = q(metoda(u,x'))$ a tú pomocou niektorej z metód náhodného vyhľadávania optimalizujeme ($u^*)$
- riešením pôvodnej metódy je $x^* = metoda(u^*, x')$


klasifikácia:
- podľa učenia
	- bez učenia - VNS
	- s učením v uzavretej smyčke (online learning) - Supra
	- s učením v otvorenej smyčke (offline learning) - natrénuje sa na množine cvičných úloh a následne sa spúšta na reálnych úlohách
- podľa konštrukcie výsledného prehľadávania
	- selection - vyberajúce heuristiky
	- generation - zostavujú prehľadávanie zo stavebných blokov
- podľa konštrukcie riešenia úlohy
	- konštruktívne - duálne
	- perturbačné - primárne
		- HH so zoznamom základných heuristík nižšej úrovne, pracuje s tabu-listom a akceptačným pravidlom
		- ![[perturbacna.png]]


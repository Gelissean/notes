- neutriedený súbor, prístup podľa transformácie kľúča
- prístup ako pri hešovaní v operačnej pamäti
- nepoužívať pri dynamických súboroch

- priamy alebo sériový (pri zreťazení) prístup

riešenie kolízií:
- otvorené adresovanie - hľadanie najbližšieho voľného miesta
- oblasť preplňujúcich blokov
	- pri kolízií sa alokuje nový blok na konci súbora, uloží sa referencia
- preplňujúci súbor
	- nové bloky sú v samotnom súbore, držia sa odkazy
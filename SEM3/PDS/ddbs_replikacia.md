podľa času (kedy)
- synchrónna
	- zmeny dát sú okamžite oznámené všetkým uzlom.
	- zmeny sú v rámci jednej transakcie, vlastnosti ACID sú aplikované na všetky aktualizácie uzlov
	1. dáta sú v konzistentnom stave vo všetkých uzloch
	2. jeden z uzlov oznámi požiadavku na zmenu
	3. požiadavka je konzultovaná ostatnými
	4. v prípade úspechu dohoda
	5. dáta sú aktualizované v každom uzle
- asynchrónna (lazy)
	- zmena najskôr na lokálnej kópií
	- neskôr zmena oznámená ostatným uzlom

podľa miesta (kde)
- decentralizovaná
	- ľubovoľný uzol môže aktualizovať dáta, ostatné sa zariadia podľa synchrónnosti
- centralizovaná
	- zmeny sa vykonávajú iba na centralizovanom uzle (jednom), ostatné odsledujú tie isté zmeny


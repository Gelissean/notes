**Externé triedenie**
- s využitím externého média (disk)
- dvojfázový prístup:
	1. transformácia vstupného neutriedeného súboru na $K$ utriedených častí (monotónie, runs), ktoré nemusia byť rovnakej dĺžky
	2. spájanie čiastkových súborov do jedného utriedeného
- pre každú monotóniu je potrebný jeden buffer a jeden pre kumulovaný zápis
- problém vyhľadania minimálneho prvku z prvkov v bufferi (možné použiť quicksort)
- všetky dáta sa dva krát načítajú a dva krát zapíšu
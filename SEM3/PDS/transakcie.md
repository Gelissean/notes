t manažment:
- odolnosť systému voči chybám spracovania
- paralelné vykonávanie viacerých transakciíí

Transakcia je považovaná za základnú jednotku práce databázového systému

```sql
begin work
  update student ...
  
commit work
```
možné chyby:
- porušenie integritných obmedzení
- chyby aplikácií
- zrušenie transakcie
- systémové chyby
- chyby média

príkazy:
```sql
begin work
commit work
rollback work
abort
savepoint
```

stavy:
- aktívna
- čiastočne potvrdená
- chybná
- zrušená
- potvrdená

životný cyklus transakcie:
1. pracovná fáza - read a write nad objektami DB, práca
2. certifikačná fáza - či je T serializovateľná a či môže byť potvrdená, iba v optimistických systémoch
3. potvrdzovacia fáza - vykoná sa commit alebo rollback

vlastnosti transakcie (ACID, atomicity, consistency, isolation, durability)
- atomicita 
	-  vykonajú sa buď všetky operácie alebo žiadna
- konzistencia
	- program transformuje DB z konzistentného stavu do konzistentného stavu
	- úrovne:
		0. neprepisuje dáta inej transakcie
		1. neprepisuje dáta inej transakcie, nepotvrdzuje žiadnu zmenu, kým nie sú ukončené všetky zmeny (commit)
		2. 1 + nečíta dáta, ktoré používa iná transakcia
		3. 2+ iné transakcie nečítajú dáta používané transakciou pred ukončením
- izolovanosť
	- transakciou zmenené dáta nezískajú iné transakcie pokým táto transakcia nie je potvrdená
- perzistancia
	- všetky potvrdené výsledky sú uložene v DB

anomálie v transakciách:
- dirty read - W1, W2, C1, C2
- non repeatable read (fuzzy read) - R1, W2, C1, C2
- phantom - R1, W2, C2, C1

izolačné úrovne:
- read uncommited
- read commited
- repeatable read
- serializable

typy transakcie:
- podľa aplikácie
	- centralizované
	- distribuované
- podľa dovy trvania
	- online (krátke)
	- batch (dlhé)
- podľa štruktúry
	- ploché
	- hniezdené

logický žurnál:
- obsahuje ID transakcie, činnosti, operácie, čas udalosti, záznamy pred, po operácií, záznam z checkpointu

Log Ahead Rule - DB objekt môže byť modifikovaný až keď sú zmeny zaznamenané v žurnále

UNDO - vráti všetky zmenené záznamy DB do pôvodného stavu
REDO - zopakuje všetky operácie vykonané v rámci transakcie

Algoritmus obnovy v prípade uvoľnenia zmien:
1. nájdi začiatok transakcie T v log. žurnáli
2. nájdi všetky započaté alebo ukončené transakcie po začiatku T
3. vráť všetky, aj ukončené transakcie do pôvodného stavu (UNDO)
4. zopakuj všetky ukončené transakcie (REDO)

metóda checkpoint:
1. všetky zmeny sú prepísané z bufferov do žurnálu
2. do žurnálu sa zaznamená záznam kontrolného bodu, obsahuje zoznam všetkých bežiacich transakcií
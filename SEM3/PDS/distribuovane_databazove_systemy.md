Distribuovaný databázový systém (DDBS)
- množina uzlov počítačovej siete, navzájom prepojených
	- každý z uzlov je samostatný DB systém, ale uzly spolupracujú tak, aby bolo z každého uzla pristúpiť na údaje ako by boli na vlastnom uzle
	- samostatná DB je množina navzájom prepojených DB na rôznych uzlov, užívateľ pracuje ako keby boli v jednej databáze

12 vlastností:
1. Lokálna autonómnosť  - v každom mieste (integrita, utajenie)
2. Nezávislosť od centrálneho uzla  - vo všetkých službách
3. Súvislá prevádzka - kontinuálny, prevádzka nenarušuje prevádzku celku
4. Nezávislosť od umiestnenia dát 
5. Nezávislosť od fragmentácie dát - používateľ nemusí vedieť, kde sú uložené fragmenty
6. Nezávislosť od replikácie dát
7. Spracovanie distribuovaných dotazov - nie je nutné presúvať dáta pre spracovanie požiadavky
8. Distribuované riadenie transakcií - dvojfázový potvrdzovací protokol (two phase commit - 2PC)
9. Nezávislosť od technického vybavenia 
10. Nezávislosť od operačného systému
11. Nezávislosť od siete
12. Nezávislosť od lokálnych databázových systémov

homogénny DDBS - všetky lokálne DB sú riadené rovnakým SRBD
heterogénny DDBS - DB nie sú riadené rovnakým SRBD

problémy DDBS:
1. Návrh distribuovaných databáz
	- dáta možno rozdeliť na replikované, nereplikvané
	- s replikáciou (plná - celá DB, čiastočná)
	- niektoré objekty možno rozdeliť na menšie časti - fragmenty (fragmentované, nefragmentované)
2. distribuované spracovanie dotazov
	- návrh samotných algoritmov, ktoré analyzujú požiadavky.
3. distrubované riadenie katalógov
	- katalógy sú metadáta DDBS, schémy lokálnych DB
	- katalógy je často nutné replikovať na všetky uzly
4. distribuované riadenie transakcií
	- transakcia môže spúšťať podtransakcie na viacerých uzloch, nutné koordinovať a zabezpečiť konzistenciu
5. distribuované riadenie paralelného spracovania transakcií
	- paralelná spracovanie prináša nutnosť synchronizovať všetky prístupy k DDBS aby bola zabezpečená konzistencia

Fragmentácia:
- horizontálna - po riadkoch
- vertikálna - po stĺpcoch (atribútoch)
- hybridná

podmienky:
- kompletnosť - každá položka nachádzajúca sa v relácií sa vyskytuje v asoiň jednom z fragmentov
- rekonštruovateľnosť 
- nespojiteľnosť - ak je relácia horizontálne dekomponovaná na fragmenty, dátová položka patrí iba do jedného fragmentu

Riadenie katalógov
- centralizované - jeden centrálny na jednom z uzlov
- plne replikované - jeden katalóg na všetkých uzloch
- čiastočné - každý uzol má vlastný katalóg pre objektu na uzle
- kombinované - každý uzol obsahuje vlastný katalóg a pre celý systém niekde existuje centrálny katalóg s kópiami všetkých lokálnych
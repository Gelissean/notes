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

distribuované riadenie transakcií
nutné zabezpečiť vlastnosti transakcie ACID
- atomicita - transakcia potvrdená iba ak sú všetky podtransakcie potvrdené
- konzistencia - DB musí byť vo všetkých uzloch v konzistentnom stave
- izolovaná vratnosť - zrušením transakcie nesmie byť postihnutá iná transakcia a zároveň musí byť zabezpečená konzistencia celej distribuovanej databázy
- trvanlivosť (durability) - zmeny sú skutočne zapísané do všetkých častí distrubovanej databázy

transakcie:
- globálna - k vykonaniu potrebuje spoluprácu s viacerými uzlami
- lokálna - potrebuje prístup k dátam jedného uzla, nespolupracuje s transakciami na iných uzloch

dvojfázový potvrdzovací protokol
- globálna transakcia môže potvrdiť svoje zmeny len ak všetky podtransakcie dosiahly bod RC (ready to commit) a vyslali hlavnej transakcií operáciu commit
- ak ktorákoľvek z podtransakcií vyšle abort, globálna musí vysielať abort všetkým ostatným podtransakciám
1. globálna transakcia spúšťa všetky podtransakcie a zbiera informácie o ukončení, nesmú sa uvoľnovať žiadne objekty
2. globálna transakcia vysiela podtransakciám ako skončiť (commit alebo abort)

protokoly
- centralizované - výsledky podtransakcií sústreďované v jednom uzle
- lineárne - jedna podtransakcia môže komunikovať len s jednou susednou, obe patria k tej istej globálnej
- distribuované - vyžaduje sa komunikácia medzi všetkými podtransakciami spustenými globálnou

na uzle, kde beží globálna transakcia rozoznávame výpadky:
- globálna T nebola schopná vyslať globálny commit/abort
	- podtransakcie musia čakať na obnovenie činnosti uzla s globálnou transakciou
	- podtransakcie, ktoré poslali lokálny abort môžu vykonať lokálny abort
	- ak nevyslali žiaden signál vyšlú abort, čaká sa na globálny abort
- globálna T už začala vysielať príkazy commit/abort
	- činnosť môžu ukončiť len tie, ktoré dostali globálny commit
	- abort môžu dokončiť len tie, ktoré dostali globálny abort
	- ak podtransakcia vyslala lokálny abort, môže ukončiť svoju činnosť, ostatné musia čakať na obnovenie globálnej transakcie

časové pečiatky zaručujú, že poradie transakcií bude zodpovedať poradiu vzniku požiadaviek

Ak na tom istom uzle udalosť i predchádza udalosť j, tak i musí mať skoršiu časovú pečiatku
ak udalosť spôsobí vyslanie správy z uzla S1 na uzol S2, tak čas prijatia správy na uzle S2 musí byť väčší ako čas odoslania na uzle S1

synchronizácia hodín pomocou viacerých metód:
- jeden z uzlov S periodicky synchronizuje čas ostatných uzlov
- lokálne hodiny na každom uzle sa inkrementujú medzi dvojicou udalostí tak, že pečiatka udalosti t1 nastaví lokálne hodiny na uzle S2 na hodnotu kde time2=MAX(t1,time2)
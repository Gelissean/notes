**Hold-out**
počiatočný súbor sa rozdelí na 2 vzorky, tréningovú a testovaciu, zvyčajne v pomere 70:30
Strata veľkého množstva údajov

**Random subsampling**
Mnohonásobný *Hold-out*. Konečný výsledok je priemerom získaných výsledkov.
Dĺhý výpočet, model je vysoko zaujatý, veľká strata dát.

**k-fold Cross Validation**
Vzorka sa rozdelí na $k$ rovnakých neprekrývajúcich sa podmnožín, z ktorých sa použije $k-1$ na vytvorenie modelu a posledná sa použie na jeho validáciu. Toto sa opakuje kým sa neprestriedajú všetky údaje na validáciu.
Nutné je mať dobre balansované dáta.
Pri malom $k$ je vyššie skreslenie výberu a malý rozptyl.
Špeciálnym prípadom je **leave-one-out** keď $k=N$

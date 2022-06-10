Data Encryption Standard
- 64b bloková šifra
- 56b kľúč, po každom kroku sa vykoná left shift buď o 1 alebo 2 miesta
- [[Feistel]]ova sieť s 16 kolami
- na začiatku sa vykoná vstupná permutácia dát, na konci jej inverzná
![[DES.png]]
![[DES_krok.png]]
- nad spracúvanými bitmi sa vykoná expanzná operácia (z každej štvorice bitov sa spraví šestica tak, že sa k ním pripojí predchádzajúci a nasledujúci bit)
- zakódované šestice sa použijú v S-boxoch (tabuľka 4×16 ($2^2×2^4$)), kde expandované bity určujú riadok a pôvodné stĺpec
- na záver sa aplikuje permutácia

možné útoky:
- hrubou silou - počet kľúčov $2^{56}$ možno prelomiť
- diferenciálnou kryptoanalýzou - zašifrovaním dvoch priamych textov a porovnávaním ich výsledkov
- v prípade dvojnásobného kódovania (2 kľúče)
	- "meet-in-the-middle" - pomocou zostavenia dvoch tabuľiek možno odhaliť kandidátov na jednotlivé bity kľúčov - dvojnásobné zosilnenie šifry neprináša očakávané zosilnenie (zložitosť je $57×2^{57}$)
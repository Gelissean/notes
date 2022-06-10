Galoisove pole (GF($2^8$)
- polynóm tpu $b_7x^7 + b_6x^6+ b_5x^5 + b_4x^4 + b_3x^3 + b_2x^2 + b_1x^1 + b_0$
- násobenie sa vykonáva ako násobenie module m(x)
- AES využíva $m(x) = x^8+x^4+x^3+x+1$
- inverzný prvok $b^{-1}$ možno vypočítať Euklidovským algoritmom
- $b^{-1}=b^{244}$
***
AES - advanced encryption standard
- bloková šifra
- 128 bitov blok
- kľúč 128/192/256 bitov
- priamy text sa delí na postupnosť 16 8bitových bajtov usporiadaných do tabuľky, rovnako aj pre kľúč (kolový kľúč)
- na každy bajt sa vykonajú dve operácie:
	1. odčítanie bitov
	2. posun riadkov o $i×8$ bitov doľava
- následne sa vykoná operácia na zamiešanie stĺpcov, kde sa celá matica vynásobí špecifickou maticou, nevykonáva sa pri záverečnom kole
- na záver sa každý bajt sčíta s príslučným bajtom kľúča
- veľkosť kľúča určuje počet kôl
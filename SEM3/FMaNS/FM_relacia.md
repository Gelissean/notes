**ohodnotená relácia**
---
- na kartézskom súčine $A\times B$  klasických množín A a B rozumieme fuzzy množinu definovanú na univerze všetkých prvkov kartézského súčinu
- rôzne volné alebo neisté vzťahy medzi prvkami oboch množín, miera tesnosti vztahu medzi dvojicou prvkov <a, b>, kde $a \in A$ a $b \in B$ je popísaná hodnotou $\mu_R(<a,b>)$.

![[fm_relacia_priklad.png]]

**skladanie relácií**
- zloženie relácií R<a,b> a P<b,c> - $R \circ P$ 
- prvkom zloženej relácie je každá dvojica <a,c>, pre ktorú existuje spoločný prvok b

![[FM_relacia_skladanie.png]]
(z prvej tabuľky sa vyberá riadok, z druhej stĺpec, vynásobia sa(minimum), výsledok je maximum)
- $\mu_{R\circ P}(<a,c>) = max\{min\{\mu_R(<a,b>,\mu_P(<b,c>)\}:b\in B\}$
- max je ľubovoľná t-conorma a min je ľubovoľná t-norma
![[FM_relacia_priklad_max-min.png]]

**princíp rozšírenia**
- využitie zobrazenia z univerza X do univerza Y
- ak $b \in Y$ neexistuje v $a \in X$ tak $f(a)=b$ a $\mu_B(b)=0$
- inak $\mu_B(b)=max\{\mu_A(a) : a\in X$ kde $f(a)=b\}$
![[FM_relacia_rozsirenie.png]]

**odvodzovanie pomocou "modus ponens"**
- ak je výrok Φ pravdivý
- a je pravdivý aj Φ -> Ω
- tak považujeme aj Ω za pravdivý

![[FM_relacia_modus_ponens.png]]
- k žltým už vypočítaným hodnotám z prvej relácie sa namiesto N pripoja nové hodnoty N'
![[FM_relacia_modus_ponens_2.png]]
vyhodnotí sa tabuľka prienikov a na záver sa vyberie maximálna hodnota zo stĺpca


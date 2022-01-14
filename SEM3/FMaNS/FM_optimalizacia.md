# optimalizačné úlohy
---
h - **hladina dôveryhodnosti**
Hodnota patrí do fuzzy čísla na hladine dôveryhodnosti ak jej funkcia príslušnosti nadobúda hodnút väčších alebo rovních hladine dôveryhodnosti

fuzzy nerovnosť sa snažíme vyjadriť pomocou parametru p(*tolerancia*) pomocou fuzzy množiny hodnôt približne menšie než a
táto množina sa označuje ako $\le a$ 
$\mu_{\le a}(f)=1$ ak $f\le a$, 
$\mu_{\le a}(f)=0$ ak $f > a+p$,
$\mu_{\le a}(f)=1-(f-a)/p$ ak $a < f \le a+p$,
---
**rozšírenie [[FM_relacia]] na fuzzy reláciu**
- ohodnotená relácia je popísaná funkciou príslušnosti $\mu_R(<a,b>)$ pre každú dvojicu prvkov <a, b>
- Fuzzy relácia bude popísaná funkciou príslušnosti $\mu_R(<a,b>)$  pre každú dvojicu fuzzy množín <a, b>, kde a je definovaná na univerze A funkciou príslušnosti $\mu_a$ a b je definovaná na univerze B funkciou príslušnosti $\mu_b$

Rozšírenie pomocou max-min prístupu
- nech a a b sú trojuhoľníkové čísla
- hodnota $\mu_\le (<a,b>) =$
$=max\{min\{\mu_a(a),\mu_b(b),\mu_\le(<a,b>)\}:a\in R, b\in R\} =$
$=max\{min\{\mu_a(a),\mu_b(b)\}:a\le b$

crisp podmienka $F(z)\le a$ sa teda nahradí ako
$\mu_\le(<F(z),a>)=max\{min\{\mu_{F(z)}(f),\mu_a(a)\}:f\le a$
![[FM_optimalizacia_LE_crisp.png]]

---
Pre maximalizáciu účelovej funkcie môžeme určiť dve reálne hodnoty F1 a F2, kde hodnoty F(z) pod F1 považujeme za malé a nad F2 za dosť veľké
Tieto hodnot sa určujú za najmenej a najviac priaznivých podmienok

Hodnotu fuzzy účelovej funkcie považujeme za dostatočne veľkú na hladine dôveryhodnosti ak jej najvyššia možná hodnota pre túto hladinu je väčšia alebo rovná najmenšej možnej hodnote z množiny dostatočne veľkých hodnôt
![[FM_optimalizacia_dostatocne_velke.png]]

---
**Tanaka-Asai**
- postupne fixujeme hodnoty h na vyššie a vyššie a vždy pre hodnotu h riešime úlohu lineárneho programovania pre pôvodné x a pre pôvodnú účelovú funkciu
- Keď úloha prestane mať prístupné riešenie končíme
- optimálne riešenie pre najvyššie posledné h je riešením úlohy

---
príklad:
potrebné určiť optimistický a pesimistický prípad pre získanie F1 a F2
![[FM_optimalizacia_priklad.png]]


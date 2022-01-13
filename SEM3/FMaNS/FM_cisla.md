**konvexná množina** - ak každý alfa-rez je konvexná množina

---
**fuzzy čísla**
- konvexná fuzzy množina, ktorej funkcia príslušnosti dosahuje hodnoty do 1 a mimo uzavretého intervalu 0 sa nazýva fuzzy číslo

**trojuholníkové fuzzy čísla**
- popísané trojicou $<c^1,c^2,c^3>$
- funkcia príslušnosti má trojuhoľníkový tvar, kde prvý a posledný bod označujú dotyčnice k základniam a druhý bod má funkciu príslučnosti rovnú 1
![[FM_cisla_trojh.png]]

**aritmetické operácie s fuzzy číslami**
![[FM_cisla_scitanie_alfa.png]]
(len s trojuhoľníkovými tvarmi)
sčítanie
$a+b=<a_1,a_2,a_3> + <b_1, b_2,b_3> = <a_1+b_1, a_2+b_2,a_3+b_3>$
odčítanie (v opačnom poradí ako sčítanie)
$a-b=<a_1,a_2,a_3> - <b_1, b_2,b_3> = <a_1-b_3, a_2-b_2,a_3-b_1>$
násobenie reálnym čislom
ak $\beta>0$ tak $\beta a = \beta <a_1,a_2,a_3> = <\beta a_1,\beta a_2,\beta a_3>$
ak $\beta<0$ tak $\beta a = \beta <a_1,a_2,a_3> = <\beta a_3,\beta a_2,\beta a_1>$

pri delení je potrebné okrajové hodnoty fuzzy čísel vydeliť každé s každým, z výsledku zrekonštruovať nové fuzzy číslo

---
**porovnávanie fuzzy čísel**
Porovnanie projekcií ťažísk:
- nájdenie ťažísk oboch fuzzy čísel,
- porovnanie ich projekcií na osu x,
- väčšie číslo má projekciu s väčšou hodnotou


Kaufmann-gupta:
- výpočet doplňkov, väčší znamena väčšie fuzzy číslo, inak
- porovnanie hodnôt s maximálnou hodnotou príslušnosti, inak
- porovnanie dĺžky základní oboch fuzzy čisel

- Výpočet doplnku:
- $D = (LD+RD)/2$
- $LD = (a_1 - k) + (b_1 - k)/2$
- $PD = (b_1 - k) + (c_1 - k)/2$
- k je ľubovoľné číslo menšie alebo rovné najmenšej hodnote porovnávaných fuzzy čísel
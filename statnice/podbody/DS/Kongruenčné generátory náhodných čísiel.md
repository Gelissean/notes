perióda - počet čísel, ktoré je generátor schopný generovať bez opakovania
plná perióda - generátor dokáže generovať všetky čísla až do hodnoty $m$
***
**Lineárny**
- $X_i = aX_{i-1} \mod m$
- ak poznáme parametre, všetky hodnoty sú vopred dané
***
**Násobný rekurzívny**
- $X_i = (a_1X_{i-1} + a_2X_{i-2}+\dots+a_kX_{i-k}+c)\mod m$
- všeobecný lineárny
***
**Fibbonacciho**
- $X_i = (X_{i-1} + X_{i-2})\mod m$
- nevhodné štatistické vlastnosti, nepoužíva sa
***
**Shift register**
- generuje bity podľa booleovského vzoru posledných generovaných hodnôt
![[shift register generator.png]]
***
**Mersenne Twister**
- vychádza z Shift register generátora
- perióda $2^{19937}-1$
- 624 násad
- generuje čísla v dávkach po 624
***
**Subtract with borrow**
- vychádza z lineárneho, veľká perióda
**Multiply with carry
- vychádza z násobného rekurzívneho
- $c = (a_1X_{i-1} + a_2X_{i-2}+\dots+a_kX_{i-k})/m - carry$
***
**Nelineárne**
- $X_i = (X_{i-1}^2)\mod m
- m je matematickým produktom prvočísel
**Kombinované**
- vychádza z dvoch pseudonáhodných sekvencií čísel, vykonávajú medzi sebou matematické operácie
**Kompozitné**
**Quasi Monte Carlo**

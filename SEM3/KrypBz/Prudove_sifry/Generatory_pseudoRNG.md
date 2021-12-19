**Generátory pseudo-náhodnej postupnosti**

 - výstup z Geiger-Mullerovho počítača
 - meranie nepravidelností silne zamestnaného servera
 - meranie teplotných fluktuácií
 Výsledky týchto meraní sú síce náhodné, ale pravdepodobnosti 0 a 1 nemusia byť rovnaké.
 
 spôsob vyrovnávania pravdepodobnosti podľa sledovania dvojíc čísel( 10 je 1, 01 je 0)
 
 *Lineárny kongruentný generátor**
 $x_n = (aX_{n-1}+b)\mod m$
 perióda max m-1
 kvadratický kongruentný generátor:
 $X_n = (aX^2_{n-1}+bX_{n-1}+c$
 
 kongruenčné generátory boli dokázané byť kryptograficky slabé \[Joan Boyar\]
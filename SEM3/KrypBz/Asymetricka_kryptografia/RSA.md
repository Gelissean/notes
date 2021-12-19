1. Účastník A volí dve tajné velké prvočísla p,q
2. $n = p*q$
3. $\phi(n) = (p-1)(q-1)$
4. zvolí dve čísla 
$0<e<\phi(n);0<d<\phi(n)$
tak, aby
$e*d = 1 \mod\phi(n)$
5. verejný kľúč účastníka A je (e,n), tajný (d,n)
6. Účastník B bude správu x < n šifrovať
$y=x^e \mod n$
7. A dešifruje správu
$x=y^d \mod n$

problémy voľny p,q
- aspoň 512-1024b
- zisťovanie prvočíselnosti

niekedy potrebné silné prvočíslo p
- p je veľké
- p-1 má veľký prvočíselný faktor; $p=a_1p_1+1$ pre veľké prvočíslo $p_1$
- $p_1$-1 má veľký prvočíselný faktor
- p+1 má veľký prvočíselný faktor

Často sa volí e = 65537 ($2^{16}+1$), je to prvočíslo
d s nájde rozšíreným euklidovým algoritmom

Nešifrovať viackrát tú istú správu
Nepoužívať spoločný n
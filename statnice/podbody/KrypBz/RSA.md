Algoritmus:
1. účastník A zvolí dve veľké tajné prvočísla $p$ a $q$
2. $n = p×q$
3. $\phi(n) = (p-1)(q-1)$
4. zvolia sa ďalšie dve čísla $0<e<\phi(n)$, $0<d<\phi(n)$, tak, že $e×d \equiv 1 \mod \phi(n)$
5. verejný kľúč je dvojica $(e,n)$
6. správa pre účastníka sa šifruje $y=x^e\mod n$
7. účastník dešifruje správu $x=y^d\mod n$

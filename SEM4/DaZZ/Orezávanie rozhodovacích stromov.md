**Error-Complexity pruning**
- 2 fázy: výroba série odrezaných stromov, výber najlepšieho variantu na nezávislých údajoch

Kvalita stromu $C_\alpha(T)$:
$$C_\alpha(T)=R(T)+\alpha×N_T$$
$T$ - časť stromu, ktorá obsahuje $N_T$ listov,
$R(T)$ - chyba klasifikácie - počet nesprávnych klasifikácií/počet klasifikovaných príkladov
$\alpha$ - reálne neznáme číslo (complexity cost, cena lista v odrezanej časti)
$$R(t) + \alpha×1=R(T)+\alpha×N_T$$
$$\alpha = \frac{R(t)-R(T)}{N_T-1}$$
Algoritmus prvej fázy:
1. vypočítať $g_k(t)$ pre každý uzol stromu $g(t) = \frac{R(t)-R(T)}{N_T-1}$
2. určiť $\alpha_{k+1} = \textrm{min}_t g_k(t)$
3. zmeniť uzly $g_k(t)=\alpha_{k+1}$ na listy, vytvorí sa nový obrezaný strom $T_{k+1}$
4. $k = k+1$
5. ak sa $T_k$ rovná koreňovému uzlu konči, inak krok 1
![[pruning.png]]

*Druhá fáza*
-výber najlepšieho variantu
$$SE(R)=\sqrt{\frac{R×daco) - R}{N}}$$
$R$ - misclassification rate odrezaného stromu
$N$ - počet príkladov v teste
***
**Minimum-Error pruning**
očakávaná chyba $E$
$$E = \frac{(n-n_c+k-1)}{n+k}$$
$k$ - počet tried
$n$ - počet testovacích príkladov
$n_c$ = počet príkladov v max triede $c$

rekurzívne sa počíta očakávaná chyba pri odrezaní a neodrezaní každého uzlu, ak je očakávaná chyba väčšia v neodrezaných vrcholoch tak sa odreže, inak nie
V prípade nerezania sa počíta pomerovo pre každý list
![[min-error-pruning-example.png]]
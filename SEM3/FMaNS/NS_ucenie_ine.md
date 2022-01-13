**učenie s predlohou**
- máme vytvorenú množinu vzorkov x a správnych odpovedí s
- riešíme úlohu vhodného nastavenia synoptických váh minimalizáciou nasledovného vzťahu
$\sum_{k=1}^{M}{(s^k-y^v(x^k))^2}$

- synaptické váhy sa poučítajú pomocou lineárnej regresie
$s^k = g(q^k)$
$(*) = \sum_{k=1}^M(s^k-g(z^v(x^k)))^2$
- namiesto odchýliek obrazov sa budú spracovať odchýlky vzorov
$\sum_{k=1}^M(q^k-z^v(x^k))^2$

$F(\omega_1^v,\dots,\omega_m^v,\theta^v)=\sum_{k=1}^M(q^k-\sum_{i=1}^m\omega_i^v.y^i(x^k)+\theta^v)^2$
Funkcia F je voči synoptickým váham ostro konvexná, ak bude mať stacionárny bod(prvé parciálne derivácie sú nulové), bude v bode minimum

$\frac{\delta F}{\delta\omega_u^v} = -2 \sum_{k=1}^M(q^k-\sum_{i=1}^m \omega_i^v . y^i(x^k)+\theta^v).y^u(x^k)$

$\frac{\delta F}{\delta\theta^v} = 2 \sum_{k=1}^M(q^k-\sum_{i=1}^m \omega_i^v . y^i(x^k)+\theta^v)$

upravením vzťahov dostávame gauss-jordanovu metódu
![[NS_ucenie_ine_gauss_jordan.png]]

![[NS_ucenie_ine_minimalizacia.png]]

**metaheuristika Simulated Annealing**
![[NS_ucenie_ine_SA.png]]
### Neurónové sieťe so spätnou väzbou
---
- jednu alebo viac vrstiev
- vstupy neurónov z jednej vrstvy môžu byť prepojené s výstupmi tej istej ale aj nasledujúcej vrstvy
![[NS_spatna_vazba.png]]

- vstup vrstvy ostáva nezmenený po dobu výpočtu všetkých výstupov siete
$$y^{t+1}=g(y^t)$$
- či sa bude pri spätnej väzbe hodnote konvergovať k 1(-1) alebo 0 záleží na sklone grafu aktivačnej funkcie, pri vysokých teplotách bude utlmovaná, pri nízkych konvergovať k 1(-1)

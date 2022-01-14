- spracovanie neistých informácií

**univerzum** - nadmnožina validných hodnôt

**Funkcia príslušnosti**
- zobrazenie hodnoty z nadmnožiny do intervalu <0;1>
- udáva stupeň príslušnosti prvku do fuzzy množiny
- značí sa $\mu(x)$ 

**operácie na fuzzy množinách**
prienik
$\mu_{D\cap B}(x) = min\{\mu_D(x), \mu_B(x)\}$
$\mu_{D.B}(x) = \mu_D(x) . \mu_B(x)$
$\mu_{D \lambda B}(x) = \mu_D(x).\mu_B(x)/max\{\mu_D(x),\mu_B(x),\lambda\})$
*(Dubois a Prade, parameter* $\lambda \in <0,1>$*)*
iné T-normy

zjednotenie
$\mu_{D\cup B}(x) = max\{\mu_D(x), \mu_B(x)\}$
$\mu_{D+B}(x) = \mu_D(x) + \mu_B(x) - \mu_D(x).\mu_B(x)$
$\mu_{D \beta B}(x) = min\{1, ((\mu_D(x))^\beta + (\mu_B(x))^\beta)^{1/\beta}\})$
*Yager, parameter* $\beta > 1$*)*
iné T-conormy

doplnok
$\mu_d^-(x) = 1-\mu_D(x)$

**normovaná fuzzy množina**
- výška fuzzy množiny je maximálna hodnota
- normovaná má výšku hodnoty 1

**Alfa-rez**
- alfa-rez D je množina všetkých prvkov univerza, ktoré majú funkciu príslušnosti väčšiu alebo rovnú hodnote $\alpha$
- $D_\alpha=\{x \in X:\mu_D(x) \ge\alpha\}$


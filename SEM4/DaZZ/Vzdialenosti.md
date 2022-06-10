**Podobnosť a vzdialenosť**
podobnosť $s$
vzdialenosť $d = 1 - s$

podmienky miery vzdialenosti:
- reflexivita: $d(p,q)=0$ ak $p=q$
- nezápornosť: $d(p,q) \geq 0$ pre odlišné $p$ a $q$
- symetria: $d(p,q) = d(q,p)$
- trojuholníková nerovnosť: $d(p,q) \leq d(p,r) + d(r,q)$ pre všetky $p$, $q$, $r$

**Euklidovská vzdialenosť ($L_2$ norma)**
$$d_{Euclidean}(p,q) = ||p-q||_2 = \sqrt{\sum_{i=1}^{n}{(p_i - q_i)^2}}$$
n - rozmerný priestor
- najbežnejšia funkcia
$$D_{squaredEuclidian}(p,q) = \sum_{i=1}^{n}{(p_i-q_i)^2}$$

*Štandardizácia Z-skóre*
$$x_{new}=\frac{x_{old}-m}{\sigma}$$
$$D_{squaredEuclidian}(p,q) = \sqrt{\sum_{i=1}^{n}{(\frac{p_i-q_i}{\sigma_i})^2}}$$
normalizácia:
$$x_{new}=\frac{x_{old}-x_{min}}{x_{max}-x_{min}}$$
vážená vzdialenosť:
$$d_{Euclidean}(p,q, w) = \sqrt{\sum_{i=1}^{n}{w\times(p_i - q_i)^2}}$$

**Manhattanská vzdialenosť**
- vzdialenosť mestských blokov, súčet absolútnych rozdielov súradníc
$$d_{Manhattan}(p,q) = ||p-q||_1 = \sum_{i=1}^{n}{|p_i - q_i|}$$
**Canberra vzdialenosť**
- vážená Manhattanská, pri fuzzy zhlukovaní, klasifikácií,
- citlivá na zmeny pri 0, odoľná voči odchýlkam
$$d_{Canberra}(p,q) = \sum_{i=1}^{n}{\frac{|p_i - q_i|}{|p_i| + |q_i|}}$$
**Chebyshev vzdialenosť ($L_\infty$ norma)**
- vzdialenosť pozdĺž najodlišnejšej dimenzie,
- obchodovanie s akciami, kryptomenami (rozdiel ziskov a strát)
$$d_{Chebyshev}(p,q) = ||p-q||_\infty = \max_{i=1,..,n}{|p_i-q_i|}$$
**Minkowski vzdialenosť ($L_r$ norma)**
- zovšeobecnenie Euklidovskej, Manhattanskej a Čebyševskej vzdialenosti
- existuje aj vážená verzia
$$d_{Minkowski}(p,q) = ||p-q||_r = \sqrt[r]{\sum_{i=1}^{n}{(p_i - q_i)^r}}$$
**Kosínová podobnosť a vzdialenosť**
- čím menší uhol, tým je vyššia podobnosť
$$s_{cos}(p,q)= \frac{p\times q}{||p||\times||q||} = \frac{\sum_{i=1}^n{p\times q}}{\sum_{i=1}^n{||p||}\times\sum_{i=1}^n{||q||}} $$
$$d_{cos}(p,q)=1-s_{cos}(p,q)$$
![[kosínová podobnosť.png]]
**Mahalanobis vzdialenosť**
- prednostné váženie určitým rozmerom
- váha pomocou inverznej hodnoty rozptylu údajov rozmeru
$$d_{M}(p,q,S) = \sqrt{(p-q)\times S^{-1}\times (p-m)^T}$$
kde $S$ je kovariačná matica
postup pre získanie $S$:
1. výpočet priemerných hodnôt každého rozmeru $m$
2. štandardné odchýlky hodnôt rozmeru $\sigma$
$$\sigma_1 = \sqrt{\frac{\sum_{i=1}^n{(a_i-m_i)^2}}{n-1}}$$
3. Výpočet kovariácie
$$cov_{(1,1)} = \sigma_1^2$$
$$cov_{(2,2)} = \sigma_2^2$$
$$cov_{(1,2)} =\frac{\sum_{i=1}^n{(a_i-m_i)\times(b_i-m_i)}}{n-1}$$
$$S = \begin{bmatrix}cov_{(1,1)}&cov_{(1,2)}\\cov_{(2,1)}&cov_{(2,2)}\end{bmatrix}$$

**Pearson korelačná vzdialenosť**
korelačný koeficient $r_{pq}$
$$r_{pq}=\frac{\sum_{i=1}^n{(p_i-\bar{p})\times(q_i-\bar{q})}}{\sqrt{\sum_{i=1}^n{(p_i-\bar{p})^2}}\times\sqrt{\sum_{i=1}^n{(q_i-\bar{q})^2}}}$$
- $n$ - veľkosť vzorky
$$\bar{p}=\frac{1}{n}\times\sum_{i=1}^np_i$$
$$\bar{q}=\frac{1}{n}\times\sum_{i=1}^nq_i$$
$$d_{cor}(p,q)=\frac{1-r_{pq}}{2}$$
**Levenshtein vzdialenosť**
- metrika merania podobnosti dvoch reťazcov
- vytvoriť tabuľku so slovami po riadku a stĺpci, zaznačiť ich dĺžku, ak sa znak riadku a stĺpca zhoduje tak cena 0, hodnota bunky je minimom z {nad +1, pod+1, diagonálne + cena}
![[Levenshtein.png]]

**Hammingova vzdialenosť**
počet odlišných znakov, manhattanská vzdialenosť pri kategorických údajoch

**Jaccardov podobnostný koeficient a vzdialenosť**
- podobnosť dvoch súborov údajov
$$s_J(p,q) = |p \cap q|/|p\cup q|;$$
$$s_J(p,q) = |p \cap q|/(|p|+|q|-|p\cap q|);$$
$$s_J(p,q) = \sum_i^n min(p_i, q_i) /\sum_i^n max(p_i, q_i)$$

**Sørensen-Dice index a vzdialenosť**
- meria podobnosť súboru vzoriek ako percento prekrytia
$$s_{Dice}=\frac{2×|p\cap q|}{|p|+|q|}$$

**Podobnosť dvojstavových premenných {0;1}**
-kvalita podobnosti určovaná pojmom koincidencie.
![[koincidencna_matica.png]]
- Rôzne indexy zhody:
1. Sokalov (simple matching coeff.) - $(a+d)/(a+b+c+d)$
2. Russelov - $(a)/(a+b+c+d)$
3. Jaccardov - $(a)/(a+b+c)$
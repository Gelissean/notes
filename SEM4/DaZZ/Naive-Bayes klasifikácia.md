$$p(B_j|A_1,\dots,A_n) = p(A_1,\dots,A_n|B)×p(B)/p(A_1,\dots,A_n)$$
- pracuje sa s tabuľkou údajov
- výsledná pravdepodobnosť sa určuje porovnaním pravdepodobnosti vstupných veličín s hodnotami vynásobených pravdepodobnosťou výsledku
- Pri zisťovaní a porovnávaní všetkých pravdepodobností sa môže menovateľ zlomku zanedbať počas normalizácie
![[Naive-Bayes.png]]

- V prípade číselného vyjadrenia atribútu(ako vek) sa pracuje s priemerom a smerodajnou odchýlkou vloženou do funkcie hustoty namiesto pravdepodobnosti výskytu daného atribútu:
$$\mu=\frac{1}{N}\sum_{i=1}^Nx_i$$
$$\sigma=\sqrt{\frac{1}{N-1}\sum_{i=1}^N(x_i-\mu)^2}$$
$$f(x)=\frac{1}{\sqrt{2\pi\sigma}}e^{-\frac{(x-\mu)^2)}{2\sigma^2}}$$

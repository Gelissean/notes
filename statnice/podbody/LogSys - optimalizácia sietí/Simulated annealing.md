**Simulated Annealing**
- preskúmaj okolie, ak je riešenie lepšie, použi ho, ak nie tak ho použi iba v prípade, že náhodný generátor vráti hodnotu menšiu alebo rovnú nasledujúcej pravdepodobnosti
$$p(x, x^i, t) = e^{-(f(x)-f(x^i))/t}$$
- $t$ - teplota, najskôr nastavená na $t^{max}$
- teplota postupne klesá podľa vzťahu $$t=t/(1+\beta t)$$

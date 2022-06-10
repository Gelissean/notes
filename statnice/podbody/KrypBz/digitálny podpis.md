- účastník A podpíse správu M tak, že k nej pripojí výsledok dešifrovania správy M svojím tajným kľúčom $$Sig(M)=D_{KT_A}(M)$$
$$M = D_{KV}(Sig(M))$$
- účastník B overí pravosť podpisu tak, že vypočíta $$M'=E_{KV_A}(Sig(M))$$
- ak $M'=M$, podpis je pravý
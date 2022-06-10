[[úloha odberných dní]]

Náklady:
- $N_f$ - fixné náklady (realizácia dodávky)
- $N_v$ - variabilné náklady (držanie nákladu v sklade)

Prečakané elemento-dni: $$T×\frac{b}{2}=T×\frac{T×h}{2}=\frac{b}{h}×\frac{b}{2}$$
Čakanie jednej jednotky nákldu jeden deň stojí $u$
$$N_v=u×T×\frac{b}{2}=u×T^2×\frac{h}{2}$$
![[odberne_dni_priklad.png]]
Optimálna veľkosť periódy $T^*$(dodávky $b^*$)
$$T^*=\min\{\frac{K^{\max}}{h}, \sqrt{\frac{2N_f}{uh}}\}$$
$$b^*=\min\{K^{\max}, \sqrt{\frac{2N_fh}{u}}\}$$![[odberne_dni_trasy.png]]
![[odberne_dni_dni.png]]

Riešením je dvojfázová heuristika:
1. určenie počiatočných priradení prípustných kombinácií dní, redukované mediány pre jednotlivé dni
2. zlepšovanie priradených prípustných kombinácií
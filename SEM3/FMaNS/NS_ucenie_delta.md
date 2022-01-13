### princíp trénovania neurónovej siete
#### (učenie s predlohou)

---
- spočíva v postupnom vyhodnocovaní reakcie neurónovej siete na jednotlivé vstupy (vzorky), v porovnávaní výstupov s príslušnými predlohami a v úprave synoptických váh tak, aby rozdieli medzi reakciou a predlohou boli minimálne
![[FM_delta_bunka.png]]
**Algoritmus učenia založený na delta prístupe**
1. inicializuj synoptické váhy $\omega$ pre všetky vstupy a hodnotu $\theta$. Nastav parametre γ (rýchlosť učenia), ε (minimálna vhodná odchýľka), r (nutný počet správnych opakovaní)
2. Vygeneruj vstupnú vzorku x(p) so správnou odpoveďou $y^*(p)$.
3. Vyhodnoť reakcie z(p) (vnútorné stavy buniek) a y(p) (výstupné hodnoty buniek) neurónovej siete na vstupnú vzorku x(p).
4. Ak je druhá mocnina rozdielu očakávaného výstupu a výstupu siete väčšia ako je povolené ε je potrebné upraviť váhy nasledovne:
$$\omega_i= \omega_i + \gamma(y^*(p)-y(p))x_i(p)$$
$$\theta=\theta-\gamma(y^*(p)-y(p))$$
5. Ak sa našlo r zhôd medzi reakciou a správnou odpoveďou tak je doučené, inak sa vráť na krok 2

dôležitá poznámka - v prípade, že v bunke sa θ pričítava, vo vzorci na kroku 4 sa zmena tiež pričítava

[[NS_delta_odovodnenie]]
Princíp spätnej propagácie je rovnaký ako pri [[NS_ucenie_delta]] ale dá sa aplikovať na viacvrstvovú sieť

Funguje rovnako ako učenie delta, treba zobecniť spôsob úprav synaptických váh tak, aby sa zistená chyba rozložila medzi jednotlivé vrstvy

Pri rozkladaní vplyvu chyby sa využíva spätný postup od výstupnej vrstvy postupne až k prvej skrytej (spätná propagácia)

algoritmus:
1. inicializuj synoptické váhy $\omega$ pre všetky vstupy a hodnotu $\theta$. Nastav parametre γ (rýchlosť učenia), ε (minimálna vhodná odchýľka), r (nutný počet správnych opakovaní)
2. Vygeneruj vstupnú vzorku x(p) so správnou odpoveďou $y^*(p)$.
3. Vyhodnoť reakcie z(p) (vnútorné stavy buniek) a y(p) (výstupné hodnoty buniek) neurónovej siete na vstupnú vzorku x(p).
4. Ak je druhá mocnina rozdielu očakávaného výstupu a výstupu siete väčšia ako je povolené ε je potrebné upraviť váhy nasledovne:
$$\omega= \omega + \gamma*h^\omega$$
$$\theta=\theta+\gamma*h^\theta$$
5. Ak sa našlo r zhôd medzi reakciou a správnou odpoveďou tak je doučené, inak sa vráť na krok 

[[NS_back-prop_odovodvnenie]]

určovanie zmien:
- najskôr sa vypočíta pre výstupnú vrstvu:
$$h(\omega_i^v)=-\phi^v(z^v(x^k))*y^{v-1,i}(x^k)$$
$$h(\theta^v)=\phi^v(z^v(x^k))$$
- následne sa postupuje až k prvej skrytej 
$$h(\omega_u^{t,r})=-\phi^{t,r}(z^t(x^k))*y^{t-1,u}(x^k) =$$
$$=-\sum_{j=1}^{m(t+1)}{\phi^{t+1,j}(z)*\omega_r^{t+1,j}} * g'(z^{t,r}(x^k))*y^{t-1,u}(x^k)$$


$$h(\theta^{t,r})=\phi^{t,r}(z^t(x^k))=$$
$$=\sum_{j=1}^{m(t+1)}{\phi^{t+1,j}(z)*\omega_r^{t+1,j}} * g'(z^{t,r}(x^k))$$

$\phi^{t+1,j}$ poznáme ako výsledok z predchádzajúcej vrstvy
Φ bunky je teda súčet súčinu vypočítaného Φ bunky z ďalšej vrstvy a príslušnej váhy smerujúcej k aktuálne spracovávanej bunke. Tento súčin sa následne vynásobí deriváciou vnútornej hodnoty z v sledovanej bunke.
V prípade počítania zmeny synaptickej váhy sa táto hodnote ešte vynásobí s hodnotou na vstupe, takže výstupné hodnoty y buniek nachádzajúcich sa na predchádzajúcich vrstvách alebo vstupoch do siete
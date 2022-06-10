- delta prístup
	- použiteľný iba pri jednovrstvovej sieti
	- Ak je odchýľka výsledku väčšia ako epsilon uprav váhy a threshold podľa vzťahov 
$$\omega_i = \omega_i + \gamma(y^*(p)-y(p))x_i(p)$$
$$\theta = \theta - \gamma(y^*(p)-y(p))$$
- back-propagation
	- upravený delta prístup na väčšiu sieť
	- počíta sa delta prístup na každý neurón zvlášť
		- posledná vrstva:
$$h(\omega_i^v)=-\phi^v(z^v(x^k))*y^{v-1,i}(x^k)$$
$$h(\theta^v)=\phi^v(z^v(x^k))$$
		- ostatné vrstvy: 
$$h(\omega_u^{t,r})=-\phi^{t,r}(z^t(x^k))*y^{t-1,u}(x^k) =$$
$$=-\sum_{j=1}^{m(t+1)}{\phi^{t+1,j}(z)*\omega_r^{t+1,j}} * g'(z^{t,r}(x^k))*y^{t-1,u}(x^k)$$

$$h(\theta^{t,r})=\phi^{t,r}(z^t(x^k))=$$
$$=\sum_{j=1}^{m(t+1)}{\phi^{t+1,j}(z)*\omega_r^{t+1,j}} * g'(z^{t,r}(x^k))$$
- iné metódy
	- učenie s predlohou - nutné poznať správne výsledky
	- úloha trénovania ako minimalizácia
	- simulated annealing - okolím sú iné hodnoty váh a thresholdu
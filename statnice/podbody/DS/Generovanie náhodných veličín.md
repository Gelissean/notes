- interval \[0, 1)
- požiadavky na metódy
	- prenositeľnosť
	- presnosť
	- robustnosť
	- efektívnosť
	- zrozumiteľnosť
	- synchrónnosť
	- monotónnosť
***
**Metóda inverznej transformácie**
- vygenerovať bod podľa distribučnej funkcie a následne vykonať inverziu
***
**Marsagliove tabuľky**
- rozdelenie generovaného spektra na tabuľky, všetky možnosti znakov (cifry) generovať samostatne podľa postupnosti. Početnosť znakov v tabuľke určuje pravdepodobnosť danej hodnoty
***
**Metóda prijatia/zamietnutia**
![[metoda zamietnutia.png]]
- generujú sa dve hodnoty
- jedna určuje hodnotu na osi X, druhá na osi Y. Dôležité je aby vygenerovaný bod so súradnicami ana osi X,Y sa nachádzal pod funkciou, ktorá má určovať pravdepodobnostné rozdelenie. Na záver sa vráti hodnota $x$.
- nemusí sa generovať z celého spektra, je možné výpočty ohraničiť
***
**Ziggurat algoritmus**
![[ziggurat.png]]
- všetky obdĺžniky majú rovnakú plochu
- generuj "hrubú súradnicu y"
- generuj súradnicu x, ktorá sa vyškáluje
***
**Kompozičná metóda**
- vyjadrenie hustoty náhodnej veličiny v tvare: $$f(x)=\sum_ip_if_i(x);p>0; \sum_i p_i=1$$
***
**Konvolučná metóda**
- generuj nezávislé hodnoty $Y_1+Y_2+\dots+Y_m$
- urči X ako $X=Y_1+Y_2+\dots+Y_m$
***
**Metódy využívajúce vlastnosti RP**
- geometrické RP s parametrom p( $0<p<1$)
***
**Polárna metóda generovania N(0,1)**
- polárne súradnice sú $R=\sqrt{x^2+y^2}$
- $\theta=tan^{-1}(\frac{y}{x})$
- $R^2 z exp(2); \theta z Uni(0,2\pi)$

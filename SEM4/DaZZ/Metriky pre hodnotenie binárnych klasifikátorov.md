**binárne klasifikátory**
V súčasnosti je jednou z najjednoduchších a najpopulárnejších [[Chybová matica]], ktorá môže pracovať s ľubovoľným počtom tried.
Na diagonále obsahuje počet správny klasifikácií, mimo diagonály nesprávnych.

V štatistike je **FP** značené ako chyba typu **1**, **TN** ako chyba typu **2**

***
**Presnosť** - počet správne označených výsledkov $\frac{TP+TN}{TP+FP+FN+TN}$
- opakom presnosti je chybovosť ($1-presnosť$)
- vhodné použiť ako metriku pri úlohách s dobrým rozložením samotných výsledných tried
***
**Citlivosť** - podieľ skutočných pozitívnych prípadov, ktoré su správne identifikované $\frac{TP}{TP+FN}$
**Precíznosť** - pozitívna prediktívna hodnota, pomer správne identifikovaných pozitívnych hodnôt $\frac{TP}{TP+FP}$
- Citlivosť a precíznosť je vhodné použit ak sa snažíme zachytiť čo najviac pozitívnych prípadov
- model s veľkou precíznosť si nemusí všimnúť pacientov s negatívnou diagnózou (nesprávnou)
***
**F-skóre**
- relatívna metrika počítajúca podiel správnej prognózy
$$F_1=\frac{2×citlivosť×precíznosť}{citlivosť+precíznosť} = \frac{2×TP}{2×TP+FP+FN}$$
Vhodné použiť ak:
- rovnaké náklady pre FP a FN
- je relatívne vysoké počet TN

- nevýhodou je rovnaká váha obom zložkám. Na základe znalosti domény je vhodné im upraviť váhy:
$$F_\beta = (1+\beta^2)×\frac{citlivosť×precíznosť}{\beta^2+citlivosť+precíznosť}$$
***
**Špecifickosť**
- metóda sa zaoberá správnou predpoveďou negatívnych prípadov
- využiť spolu s citlivosťou
- Metóda nedáva pozor na nesprávne označené pozitívne prípady, pozor na 100% špecifickosť
***
**Vyvážená presnosť a G-mean**
- založená na citlivosti a špecifickosti
$$Balanced Accuracy = \frac{1}{2}×(citlivosť+špecifickosť)$$
- skóre od 0 po 1, najlepšie 1
- použiť ak máme nevyvýžené údaje
Geometrický priemer
$$G-mean = \sqrt{citlivosť×presnosť}$$
***
**Matthews korelačný koeficient (MCC)**
- rovná sa 1 ak je predikcia blízka a -1 pri inverznej predpovedi
$$MCC=\frac{TP×TN-FP×FN}{\sqrt{(TP+FP)×(TP+FN)×(TN+FP)×(TN+FN)}}$$
- použiť ak má vzorka veľmi rozdieľnu veľkosť, triedy su nevyvážené
- často sa vykytuje pri predpovedaní chorôb a detekcií anomálií
***
**Reciever Operator charakteristika**
- nepoužíva sa pre klasifikátori s cieľovou triedou ale v prípade pravdepodobností cieľovej triedy (ako neurónové siete)
- použiť na výber optimálnych modelov pre rozdelenie tried


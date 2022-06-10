**Maximálna chyba**
- zvyšková metrika, zachytáva najhoršiu chybu medzi predpokladanou hodnotou ($\^{y}_i$) a a skutočnou hodnotou ($y_i$).
- V dokonalom modeli je hodnota 0
- nepodporuje multioutput

**Mean absolute error**
- priemerná chyba
- pohybuje sa od 0 po $\infty$
- priamejšia reprezentácia súčtu chybových pojmov
- najodolnejší voči odľahlým hodnotám

**Mean absolute percentage error**
- podobná MAE, berie percentuálnu chybu a nie absolútnu hodnotu

**Mean squared error/Root mean squared error**
- MSE vychádza z predpokladu, že chyby sledujú normálne rozdelenie
$$MSE(y,\^{y}_i) = \frac{1}{n}\sum^n_{i=1}(y_i-\^{y}_i)^2$$
- RMSE je druhá odmocnina z MSE
- používa sa častejšie, menšie hodnoty sú lepšie na porovnávanie

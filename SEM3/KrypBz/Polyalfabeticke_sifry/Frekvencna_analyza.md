Na počítanie šifier sa využíva fakt, že výstupom často býva šifra konkrétnych textov.
V každom jazyku existuje nejaké rozloženie pravdepodobností jednotlivých znakov a to sa nazýva súborom pravdepodobností $P(x_1, x_2, \dots , x_n)$
Súčet jednotlivých pravdepodobností sa rovná jednej

Stredná informácia na jedno písmeno je
$H_1 = \sum_{x_1}{-P(x_1) log_2 P(x_1)}$

Pri sledovaní dvojíc za sebou idúcich znakov je to informácia na dvojicu:
$H_2 = \sum_{x_1}{\sum_{x_2}{-P(x_1, x_2)log_2P(x_1,x_2)}}$

stredná informácia na znak je
$H=\frac{1}{n} H_n$

Náš odhad $H$ (slovenského jazyka) je 1,57\[bit/znak\], $\kappa = 0,0553$
![[Frekv_analyza.png]]
![[Frekv_analyza_trojice.png]]

V slovenskej abecede je najčastejšie využívaný znak medzery a "a".
- Ak bola využitá permutácia s medzerou, treba analyžovať kratšie slová
- Hľadať časté kombinácie znakov (trojice, štvorice), často na koncoch a začiatkoch slov
- Odhad niektorých slov

Samohlásky možno nájst:
- samohlásky sú obkolesené spoluhláskami,
- spoluhlásky samohláskami
- písmená s malým počtom rôznych susedov sú samohlásky
- skoro v každom slove je samohláska

![[mat_form_frekv_analyzy.png]]

**Index koincidencie**
spôsob ako kvantifikovať mieru nerovnomernosti pravdepodobností

$\sum_{i=1}^q (p(a_i)-\frac{1}{q})^2$

pre q = 26
$\sum_{i=1}^{26} p(a_i)^ - 0,038462$
pre slovenskú telegrafnú abecedu - 0,06027
pre slovenskú abecedu s diakritikou, číslami a interpunkcnými znamienkami 0,0553
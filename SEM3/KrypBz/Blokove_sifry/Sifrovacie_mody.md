existuje niekoľko spôsobov ako vytvoriť zodpovedajúcu postupnosť blokov zašifrovaného textu

**ECB - Electronic Code Book** mód
najjednoduchší, šifruje sa blok po ploku predpisom $y_i = E_K(x_i)$
a dešifruje $x_i = D_K(y_i)$
rovnaký blok sa zakaždým zašifruje na rovnaký blok, môže uľahčiť útoky

**OFB - Output Feedback** mód

najskôr sa zvolí náhodný inicializačný blok (IV - *inic. vektor*)
postupne sa počítajú $z_1 = E_K(y_1)$
a rekurentne $z_{i+1} = E_K(z_i)$
šifruje sa predpisom
$y_i = z_i (+) x_i$
zašifrovaná správa má o jeden blok viac,
dešifruje sa
$x_i = z_i (+) y_i$
pripomína šifru prúdom kľúčov, pre každú správu treba iný inicializačný vektor

**CBC - Cipher Block Chaining** mód
šifruje sa predpisom
$y_i = E_K(y_{i-1})(+)x_i$
zašifrovaná správa ma o jeden blok viac (inicializačný)
dešifrujeme
$x_i = y_i (+) E_K(y_{i-1})$
![[CBC_example.png]]
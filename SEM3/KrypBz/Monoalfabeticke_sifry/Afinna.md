
$y = E_{k_1,k_2}(x) = (x (*) k_1) (+) k_2)$
$x = D_{k_1,k_2}(y) = (y (-) k_2) (*) k_1^{-1}$

$k_1 \in \{1, 3,5,7,9,11,15,17,19,21,25\}$
12 možností, nie párne, 13 a 26
$k_2 \in \{0,1,2,\dots,24,25\}$
26 možností

použiteľné kľúče: $12 * (26-1) = 311$ prvkov

slabý kľúč $(k_1, k_2) = (1,0)$


V prípade, že poznáme pôvodný text možno kľúče dopočítať
$k_1 (*) 15 (+) k_2 = 17$
$k_1 (*) 5 (5) k_2 = 11$
odčítaním týchto rovníc dostaneme rovnicu pre $k_1$:
$k_1 (*)10 = 6$
10, nemá inverziu, pomôžeme si nájdením riešenia v tabuľke
![[afinne_tabulka.png]]
dosadením do vzorca získavame $k_2$
$11 (*)5(+)k_2 = 11$
$55(+)k_2 = 11$
$k_2 = 11 (-) 55 = (-) 44 = 8$
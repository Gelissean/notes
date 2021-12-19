Sovietsky kryptosystém zo studenej vojny

64b blok, 256b kľúč
Feistelova sieť s 32 kolami,
s-boxy sú jednoriadkové tabuľky s permutáciami čísel 0-15

![[DES_GOST.png]]

kľúč možno rozdeliť na 8 32b, ktoré sa používajú dokola v poradí, na konci v opačnom poradí:
$K_1, K_2, \dots, K_8, K_1, K_2, \dots, K_8, K_1, K_2, \dots, K_8, K_8, K_7, \dots, K_1$
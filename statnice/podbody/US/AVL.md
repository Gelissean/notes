- maximálne o 45% vyšší než dokonale vyvážený
- výška ľavého podstromu a pravého podstromu sa líšia najviac o 1
- najhoršia zložitosť **O(log2 n)**
- každý vrchol eviduje informáciu o vyváženosti (-1, 0, 1)
- vhodný pre vyhľadávanie
- pri vkladaní, ak je vyvažovací faktor +/- 2 vykonáva sa vyvažovanie pomocou rotácií
![[AVL_rotacie.png]]
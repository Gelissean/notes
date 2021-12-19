64b blok vstupných dát
128b kľúč
vstupný blok sa rozdelí na 4 16b časti, s ktorými sa urobí 8 kôl a jedno polovičné
![[IDEA_sifrovanie.png]]

**generovanie kolových kľúčov**

každé kolo potrebuje 6 a polovičné 4 kľúče
(6\*8 + 4 = 52 16b kľúčov)
1. 128b kľúč rozdeli ná 8 16b
2. ľavým rotačným posunom o 25b sa získa ďaľších 8 kľúčov
3. znova rotácia o 25b pre ďaľších 8
4. atď

Dešifrovanie rovnakým algoritmom, ako kľúče sa použivajú ich inverzné hodnoty vo vhodnom poradí
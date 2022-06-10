Pre fuzzyfikáciu hodnôt je potrebné vyzbierať údaje ohľadom veličiny, ktorá má byť fuzzifikovaná
![[Fuzzify_data.png]]
Algoritmus fuzzyfikácie:
1. Tvorba vektora $\mathbfit{K}$ , obsahuje súčtové hodnoty pre každú lingvistickú premennú
$\mathbf{K}=[4,6,4,0,5,4,5,3,3,6]$
2. výber maximálnej hodnoty vo vektore $\mathbfit{K}=6$
3. transformácia hodnôt stĺpcov podľa pravidla $$c_{i,j}=b_{i,j}×k_{max}(k_j)$$
- Ak sa v stĺpci nenachádzajú žiadne dáta, nutno aproximovať
![[fuzzifikacia_transformacia_1.png]]
5. Výber maximálnej hodnoty $c_{i,j}$
6. Normalizácia hodnôt do rozsahu $<0;1>$
![[fuzzyfikacia_normalizacia.png]]

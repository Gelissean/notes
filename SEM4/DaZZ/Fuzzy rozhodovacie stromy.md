![[Fuzzy_tree_inputs.png]]
$M(A_{i,j})$ značí príslušnosť do vybranej lingvistickej hodnoty daného atribútu
$N$ - počet záznamov v tabuľke

**Informácia**
súčtová - $\mathbfit{I}(A_{i,j}) = -log_2M(A_{i,j})$
personálna - $I(A_{j,1}) = log_2N-log_2M(A_{i,j})=log_2N+\mathbfit{I}(A_{i,j})$
spoločná (joint) - $I(A_{i1,j1}, A_{i2,j2}) = log_2N-log_2M(A_{i1,j1}×A_{i2,j2}=log_2N+\mathbfit{I}(A_{i1,j1}, A_{i2,j2})$
podmienená (condition) - $I(A_{i1,j1}| A_{i2,j2}) = I(A_{i1,j1}, A_{i2,j2})-I(A_{i1,j1})$
vzájomná - $I(A_{i1,j1}; A_{i2,j2}) = I(A_{i1,j1})-I(A_{i1,j1}|A_{i2,j2})$
                 - $I(A_{i1,j1};A_{i2,j2}) = I(A_{i1,j1}) + I(A_{i2,j2}) - I(A_{i1,j1},A_{i2,j2})$
                 - $\mathbfit{I}(A_{i1,j1}; A_{i2,j2}) = \mathbfit{H}(A_{i2})-\mathbfit{H}(A_{i2}|A_{i1})$
                 - $\mathbfit{I}(A_{i1,j1}; A_{i2,j2}) = \mathbfit{H}(A_{i2})+\mathbfit{H}(A_{i1})-\mathbfit{H}(A_{i2},A_{i1})$

**Súčtová entropia**
personálna - $\mathbfit{H}(A_i) = \sum_{i=1}^{m_i}M(A_{i,j}×I(A_{i,j})$
spoločná (joint) - $\mathbfit{H}(A_{i2},A_{i1})=\sum_{j1=1}^{m_{j1}}\sum_{j2=1}^{m_{j2}}M(A_{i1,j1}×A_{i2,j2})×I(A_{i1,j1},A_{i2,j2})$
podmienená (condition) 
 - $\mathbfit{H}(A_{i2}|A_{i1,j1}) = \sum_{j2=1}^{m_{j2}}M(A_{i1,j1}×A_{i2,j2})×I(A_{i2,j2}|A_{i1,j1})$
 - $\mathbfit{H}(A_{i2}|A_{i1}) = \sum_{j=1}^{m_{i1}}\mathbfit{H}(A_{i2}|A_{i1,j1}) = \mathbfit{H}H(A_{i1},A_{i2})-\mathbfit{H}(A_{i1})$
***
**Algoritmus stavby stromu:**
1. výpočet súčtovej podmienenej entropie
2. Výber atribútu $A_i$ s najmenšou hodnotou entropie
3. určiť atribút ako uzol
4. Vytvoriť listy pre každú množinu atribútu a vykonať cyklus rekurzívne

Ak je frekvencia vetvy menšia ako prahová hodnota, uzol sa mení na list.
Ak je frekvencia triedy väčšia alebo rovná ako prahová, uzol sa mení na list.

Frekvencia vetvy je určená informáciou získanou v danej vetve $I(U_q)$
$$I(B_j,U_q)=-log_2M(B_j×A_{i1,j1}×\dots×A_{iq,jq})$$
V prípade usporiadaného stromu sa používa maximálna hodnota informácie alebo minimálna hodnota entropie pre všetky vety spoločne
***
Pri vyhodnocovaní záznamu sa prechádza celým stromom, výsledné hodnoty každého listu sa prenásobia súčinom hodnôt funkcií príslušnosti, pomocou ktorých sme sa k výsledku. Následne sa výsledky všetkých listov sčítajú.
![[Fuzzy_strom_vyhodnotenie.png]]

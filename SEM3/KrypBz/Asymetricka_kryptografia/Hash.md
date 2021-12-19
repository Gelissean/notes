V kryptografii sa ku každej správa vkladá odtlačok správy tvorený hashovacou funkciou

h(M)
- pre každé M je ľahké vypočítať h(M)
- pre každé h je ťažké nájsť M
- Pre každé M je ťažké nájsť iné M', tak aby h(M)=h(M')
- ťažké nájst 2 rôzne náhodné správy M!=M' aby h(M)=h(M') \[collision resistance, odolnosť voči kolízii\]

Dvojica správ M, M' kde h(M)=h(M') sa nazýva kolízia

**Narodeninový útok**
1. útočník vytvorí dve zmenky, za 100 a za 1000€
2. v obidvoch zmenkách bezvýznamnými zmenami robí zmany kým nenájde kombináciu kde obe majú rovnakú odtlačok
3. dlžníkovy dá potvrdiť 100€ variant
4. vymáha 1000€ variant pretože má rovnaký odtlačok

Pred podspisom digitálneho dokumentu vždy urobiť malú zmenu.

**Tvorba odtlačku**:
1. správa sa rozdelí na rovnako dlhé bloky m
2. hashovací algoritmus má pevne stanovený inicializačný vektor $h_0=IV$
3. rekurzívne počítame $h_i=f(m_i,h_{i-1})$
4. výsledný odtlačok správy $h(M) = h_k$
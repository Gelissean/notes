Blok musí mať párny počet bitov

Každý blok sa rozdelí na dve rovnako dlhé častí, ľavú a pravú,
šifrovanie prebieha v kolách
$R_{i+1} = L_i (+) f(R_i, K_i)$
$L_{i+1} = R_i$
![[Feistel.png]]

Rovnaký algoritmus je možné použiť na šifrovanie a dešifrovanie, pri dešifrovaní sa vymení poradie blokov

Dôležitou funkciou je funkcia $f(R_i,K_i)$, závisia na nej kryptografické vlastnosti celej Feistelovej siete.
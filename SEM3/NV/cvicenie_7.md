Vytvorte interpreter [Petriho sietí](https://en.wikipedia.org/wiki/Petri_net "https://en.wikipedia.org/wiki/petri_net"), ktorý bude odrážať jej základnú filozofiu:

Petriho sieť je bipartitný graf, ktorého vrcholy sa delia na miesta a prechody. Orientovanou hranou je spojený vždy miesto a prechod (nikdy nie 2 prechody alebo 2 miesta). Miesto, z ktorého hrana vychádza sa volá výstupné miesto; miesto, do ktorého hrana vchádza, sa volá vstupné miesto. V každom mieste sa môžu nachádzať značky (žiadna, jedna, viac). Ak sa vo všetkých výstupných miestach (incidentných s prechodom) nachádzajú značky, potom sa tento prechod odpáli (v čase t), vykoná sa činnosť spojená s prechodom, a vložia sa značky do vstupných miest.

-   Umožnite definovať topológiu siete a počiatočné značenie (rozloženie značiek).
-   Umožnite, aby pri odpálení prechodu bolo možné vykonať nejakú činnosť.
-   Umožnite zadať pravdepodobnosť odpálenia prechodu vo forme náhodnej premennej.

Tím E (my):
![[cv_9_E.png]]

Tím C:
![[cv_9_C.png]]
Tím B:
![[cv_9_B.png]]
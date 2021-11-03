composite

Umožňuje klientom správať sa rovnako k jednotlivým objektom ale aj k ich kompozíciám

Použiť ako chceme reprezentovať hierarchiu typu časť-celok alebo ignorovať rozdiely medzi celkom a jednotlivcom

![[composite_implementacia.png]]

Zjednodušuje klienta, netreba rozlišovať zložitosť objektu, zavádza prílišné zovšeobecnenia

Príbuzné vzory
[[Chain_of_responsibility]] - často vo vzťahu otec-syn
[[Decorator]] - často spoločná rodičovská trieda, dekorátor implementuje časť rozhrania Kompozitu (add, remove, get child)
[[Flyweight]] - zdieľanie komponentov, nemôžu referencovať rodiča
[[Iterator]] - prechody kompozitom
[[Visitor]] - sústreduje operácie a správanie

![[Composite_vzor.png]]


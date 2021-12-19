Dependents, Publish-Subscribe, Pozorovateľ, Listener (java)

Definuje vzťah 1:n tak, že jeden objekt keď zmení stav, tak jeho pozorovatelia dostanú o tom správu

Použiť keď:
- máme aspoň dvoch účastníkov, keď jeden je závislý na druhom
- zmena jedného vyžaduje zmenu viacerých
- ak je potrebné notifikovať ostatné objekty

![[observer_implementacia.png]]
Každý pozorovaný (observable) musí podporovať pripnutie pozorovateľa, odopnutie a notifikáciu, môže byť vnorená trieda, adaptér

Umožnuje nezávisle meniť pozorované a porovateľné objekty.
Abstrahuje sa vzťah medzi pozorovaným a pozorovateľom
Jednoduché upozornenie pozorovateľov
Pozor na nevyžiadané notifikácie
Môže nastať kaskádovanie notifikácií, dôležité sa nezacykliť

Príbuzné vzory:
- [[Mediator]] - rozhranie `observable` sa stáva mediátorom
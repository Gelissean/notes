Chain of responsibility
reťaz zodpovednosti

- zabraňuje previazaniu odosielateľa požiadavky s príjemcom, umožnuje požiadavku spracovať viacerým objektom, reťazí príjmateľov a posúva požiadavku pokým ju niekto nespracuje

- ak chce študent nechať uznať známky z predmetu, za kým má ísť?

vhodné použiť keď:
- viac ako jeden objekt môže spracovať požiadavku a nie je známy
- požiadanie o spracovanie požiadavky bez toho, aby sme spracujúci objekt explicitne uviedli
- ak množina objektov spracujúcich požiadavku je definovaná dynamicky

![[chain_of_responsibility_implementacia.png]]

- redukuje sa previazanosť objektov
	- odosielateľ nemusí poznať príjemcu, vie, že sa dostane na správne miesto
	- príjemca nemusí poznať odosielateľa ani štruktúru reťaze
- pridáva funkčnosť distribuovaním kompetencií medzi jednotlivé objekty, umožnuje zmeny za behu
- nemožno sa spoliehať, že požiadavka bude obslúžená konkrétnym objektom, alebo že bude vôbec obslúžená

Príbuzné vzory:
- [[Composite]] - často sa spájajú, rodič komponentu (iný komponent) slúži ako nasledovní v reťazi
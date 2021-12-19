"Mušía váha"
Štrukturálny vzor

umožnuje výrazne šetriť pamäť počítača
umožnuje veľké množstvo granulovaných objektov (veľa atribútov)

Pomocou zdieľania vnútornej časti objektov umožní mať veľké množstvo veľkých objektov

Napríklad pri textovom editore (font, rez, ...)
Čo písmeno, to inštancia triedy `znak`.

Predstavuje zdieľaný objekt
Písmeno sa rozdeľuje na stavy:
- vnútorný - uložený v "Mušej váhe", nezávislé na kontexte ("červený tučný text")
- vonkajší - uložený a závislý na Klientovi ("ja som písmeno b")
![[flyweight_ukazka.png]]

Flyweight vnáša chaos do návrhu, veľké množstvo nových tried
Vhodné použiť iba ak:
- Ak aplikácia používa veľké množstvo objektov
- Ak sú s uložením objektov veľké náklady
- Ak máme skupiny objektov s niekoľkými zdieľanými vlastnostami
- Nové zdieľané objekty musia byť čo najväčšie
- Aplikácia sa nepolieha na identitu objektov

![[Flyweight_implementacia.png]]
Objekt musí byť rozdelený na 2 časti (Extrinsic, Intrinsic) (v obrázku sú popisy naopak)
Klient musí flyweight-u dodať vonkajšiu časť
Potrebná továreň na vnútorné flyweight stavy (aby neboli duplikáty)

Za nižšie pamäťové nároky platíme výpočtom (dohladávanie zdieľaných objektov)
Čím viac zdieľam, tým lepšie; čím menej zdieľaných objektov, tým lepšie; pozor na granularitu a zvýšené výpočtové náklady

Príklad:
Simulácia chodcov - 10 000 objektov ľudí, ak sa urobí reprezentant skupiny ľudí, šetrí sa veľa miesta na atribútoch (__študent__, jeho preferencie)

Príbuzné vzory:
[[Composite]] - často sa používajú spolu, tvorí sa orientovaný acyklický graf
[[State]] a [[Strategy]] - často sa implementujú ako Flyweight
**Bridge**

Decouple an abstraction from its implementation so that the two can ary independantly

oddeľuje abstrakciu od implementácie, obe zložky možno nezávisle meniť
![[Bridge_planovac_procesorov_ukazka.png]]
Príliš rýchlo sa rozširuje, pridanie nového typu plánovača vyžaduje veľa nových tried

jedna úroveň čo, druhá úroveň ako
![[bridge_rozdelenie_ukazka.png]]
Sprostredkovávanie plánovania preventívnych/nepreemptívnych procesov oddelené od toho, kto to vykonáva (systém - linux, windows...)

bridge nutné zaimplementovať hlboko do kódu, ťažko vložit do už vytvoreného programu
V prípade možnosti použitia bridge je lepšie s ním plánovať od začiatku.

Vhodné použiť pri zabráneniu pevného prepojenia abstrakcie a implementácie
Zabraňuje veľkému rozširovaniu kódu
Zmeny v abstrakcií alebo implementácií neovplyvňujú klienta.
Dobre skrýva implementačné detaily
![[bridge_implementacia1.png]]

príklad:
môžeme mať veľa dátových štruktúr. Na ich správu možno vytvoriť triedu (interface), ktorá bude alokovať a dealokovať miesto v pamäti.
Môžeme mať veľa rôznych manažérov pamäti: operačná pamäť, súvislá operačná pamäť, súbor, ... . S memory manažérom môže pracovať nejaká pamäťová organizácia (lineárna, hierarchická, ...)
So samotnou pamäťou možno vytvoriť rôzne dátové organizácie (tabuľka, prior. front, pole, ...)
![[bridge_priklad.png]]
Ak poviem insert v tabuľke, tá povie lineárnej organizícií vlozposledny a tá povie súvislej operačnej pamäte...

Využitie napríklad pri driveroch, zmena za behu (pri pripojení novej tlačiarne možno použiť správny driver)
![[bridge_priklad2.png]]

Príbuzné vzory:
[[Abstract_factory]] - "vytvor sekvencnu tabulku v subore", vie vytvoriť správne triedy a spojí ich (zapúzdruje)
[[Adapter]] - (adaptér prepojuje 2 závislé triedy, ľahko vložiť do programu)
(bridge prepojuje 2 nezávisle domény, ľahko vložiť iba pri začiatku)
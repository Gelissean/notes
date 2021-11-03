Proxy

zástupca
obálka iného objektu, kontroluje prístup k objektu
v textovom dokumente s veľkými obrázkami - obalí objekt obrázku, načíta ho až keď sa k nemu prehliadač dostane, nemusí byť obrázok v pamäti stále

![[proxy_motivacia.png]]
draw sa zavolá až keď je to nutné, šetrí to zdroje.
aplikačné oblasti:
1) vzdialený zástupca - ambassador - zapúzdruje komunikačné údaje, objekt je napr. na inom stroji
2) virtuálny - vytvára náročné objekty až keď treba
3) ochranný - zakryje niektoré schopnosti objektu (po zavolaní draw nemusí vykresliť, napr. podľa práv)
4) chytrý odkaz - obaľujú objekt, koľko objektov referuje na tento objekt, atď. posledný objekt, ktorý ukazuje na proxy objekt zahodí proxy

![[proxy_implementacia.png]]
ako adaptér, ale má rôzne chovanie

zavádza nepriamu komunikáciu s objektom

princíp copy-on-write:
	znižuje nároky na kopírovanie objektov (napr. stromovej štruktúry)
	neurobí kópiu okamžite
	vytvorí sa proxy tabuľka a bude schopná identifikovať či došlo k zmenám. Pri čítaní je možno čítať z tej istej, kópia sa vytvorí až keď sa dátové štruktúry nezhodujú
![[proxy_copy_on_write.png]]

príbuzné vzory:
[[Adapter]] - identické rozhranie k objektu, zástupca však môže odmietnuť niektoré správy
[[Decorator]] - dekorátor pridáva funkčnosť, zástupca môže obmedziť funkčnosť

Proxy
Decorator

behaviorálny vzor
umožnuje dynamicky pridávať funkcie k objektu, alternatíva k dedeniu

textový editor - ak chcem text, môže byť vyplnený, ohraničený, atď. .
text sa postupne obaľuje niečím, čo pridáva funkčnosť.
![[decorator_motivacia.png]]
Náhradou dedičnosti za kompozíciu sa vyhneme rastu dedičnosti
![[decorator_motivacia_upravena.png]]
![[decorator_postupnost.png]]
Zo stromovej štruktúry sa stane zoznam, samotný text je vždy posledný

Použiť ak chceme pridávať funkčnosť bez obmedzenia ostatných objektov
Možno potlačiť niektoré činnosti objektu (napríklad dekorátor stop, ktorý zakáže vykreslenie textu(predefinuje zobraz() tak, aby nevolala ďalšiu))
Ak nechceme použiť dedičnosť.
![[decorator_implementacia.png]]

možno navrhnúť decorator ako adapter, potom je vykonávanie nutné posunúť ďaľšiemu prvku

Je to pružnejšie ako dedičnosť (nedochádza ku kombinatorickej explózií tried)
Dôležité nedekorovať všetko (tvorba "superdecorator"-u)
Môže sa stratiť identita tried.
Vytvára sa flexibilný systém, ktorý môže byť náročnejší na pochopenie a ladenie.

Podobné vzory:
[[Adapter]] - dekorátor mení správanie, adaptér rozhranie
[[Composite]] - dekorátor je zdegenerovaným kompozitom
[[Strategy]] - alternatíva k dekorátoru, napr (akým spôsobom zaplatiť). Dekorátor pridáva funkčnosť, stratégia mení.

Decorator

decorator
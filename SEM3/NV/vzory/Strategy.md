Stratégia
Behaviorálny vzor

Definuje rodina algoritmov (rôzny prístup k riešeniu toho istého problému)
Počas behu možno vymenením stratégie riešiť problém inými spôsobmi.

Napríklad platenie v internetových obchodoch (karta, paypal, dobierka, bitcoin, atď.)

Aplikovať keď:
- množstvo tried sa líši iba v ich správaní
- pri viacero verzií algoritmu
- zapúzdrenie stratégií

![[Strategy_implementacia.png]]

Alternatíva k dedičnosti, redukuje vetvenie kódu.

![[strategy_priklad_chodci.png]]

Príbuzné vzory:
[[Flyweight]] - stratégie sa často implementujú ako mušie váhy
[[Bridge]] - sú podobné, stratégia je behaviorálny vzor, most spája trvalé súčasti aplikácie (štrukturálny vzor)
prototype

špeciálny objekt pomocou, ktorého sú tvorené jeho kópie

Niekedy nemusí byť vhodné tvoriť veľké konštruktory alebo nové triedy.
- serializácia
- klonovanie (shallow / deep)

Použiť ak je trieda známa až za behu programu, nechceme zbytočne tvoriť mnoho tried, alebo sa menia vlastnosti objektov iba zriedkavo.

![[prototype_implementacia.png]]

Skrýva triedu výsledného produktu, ktorý nemusí byť samotná trieda

Príbúzné vzory
[[Abstract_factory]] - alternatívy, ale môžu aj spolupracovať, továreň spravuje prototypy
[[Composite]] a[[Decorator]] - pravdepodobne sa ich funkcia dá uplatniť aj Prototyp

Prototype
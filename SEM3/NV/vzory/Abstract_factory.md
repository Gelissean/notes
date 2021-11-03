Abstract factory
kreačný návrhový vzor

Rozhranie pre tvorbu rodín objektov, bez uvedenia konkrétnych tried

Umožnuje rôzne módy Look and feel
Využitie jednotlivých komponentov nemôže byť napísané pevne.

Použiť keď je systém nezávislý od toho, ako sú jeho produkty vytvárané, systém je konfigurovateľný rodinou príbuzných produktov, spoločné použitie

![[Abstract_factory_implementacia.png]]

Klientský kód je nezávislý na konkrétnej implementácií produktu, klient pracuje iba so všeobecným rozhraním.

Umožnuje jednoducho vymienať rodiny produktuv bez nutnosti upravovať klientský kód

Je náročné pridať nový druh produktu, je nutné ho pridať do každého potomka továrne

Príbuzné vzory:
[[Factory_method]] a [[Prototype]] - AT často využíva továrenské metódy alebo klonuje prototypy

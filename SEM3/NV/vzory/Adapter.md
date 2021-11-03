**Adapter**
prevádza jedno rozhranie na druhé

![[adapter_ukazka.png]]
Jednoducha aplikácia, ktorá kreslí jednoduché tvary a chce z externej knižnice kresliť text.

![[obrazky/adapter_implementacia.png]]
adaptee1 si špecifikuje svoje vlastné metódy,
adaptee2 ich dedí z adaptéru

![[adapter_implementacia2.png]]
Vytvoriť potomka z pôvodnej triedy a definovať metódy, ktoré budem realizovať
![[adapter_ukazka2.png]]

Možno adaptovať len triedu, ktorá sa zdedila, nie `textik`, ale možno upraviť triedu Text

V možnosti 2 prichádzame o možnosť prepisu triedy Text, ale možno využívať `textik` alebo `velkyText`

Náročnosť adaptéru závisí od zložitosti rozhrania
Agregácia(kompozícia) s adaptérom platí na všetkých potomkov triedy, má dlhší prístup k dátam a náročnejsí prístup k implementácií

![[adapter_viacsmerny_procesory.png]]
ak vykonáva SSE inštrukcie, možno rovno zavolať pri inteli, ak Alti inšutrkcie, tak treba skonvertovať

príbuzné vzory:
[[Bridge]] - tvorí ...
[[Decorator]] - v prípade viacerých dekorátorov, rekurzívna kompozícia dekorátorov
[[Proxy]] - definuje zástupci pre iný objekt a nemení jeho rozhranie (adapter na obrázku)

![[adapter_implementacia3.png]]

Adapter

Adapter

adapter
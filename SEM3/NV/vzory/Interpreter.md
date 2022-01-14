Interpreter

- reprezentácia gramatiky daného jazyka s interpretrom, využívajúcim túto reprezentáciu a interpretuje jej vety v tomto jazyku

- ak je namiesto vytvárania inštancií tried vhodné popísať problém pomocou jednoduchých viet vo vlastnom jazyku a zostaviť interpreter, ktorý takýmto vetám porozumie
- príkladom je vyhľadávanie reťazca zodpovdajúceho zadanej maske
- interpretej popisuje ako definovať gramatiku jednoduchého jazyka a reprezentovať jednotlivé vety, ktoré bude interpretovať

![[interpreter_gramatika.png]]

![[interpreter_syntakticky_strom.png]]

vhodné použiť keď existuje jazyk, v ktorom sa dajú jednoducho previesť výrazy do formy syntaktického stromu keď:
- existuje jednoduchá gramatika jazyka, zložité hierarchie spôsobia vytvorenie komplikovanej štruktúry tried syntaktického stromu
- efektívnosť nie je kritickým prvkom návrhu systému, často sa vety netransformujú do syntaktického stromu priamo, ale najskôr podľa pomocných štruktúr, je to pomalšie

![[interpreter_implementacia.png]]

- jednoduché implementovať a rozšíriť gramatiku, je vo forme tried
- komplexné gramatiky je ťažké udržiavať
- rovnaký syntaktický strom možno interpretovať rôznymi spôsobmi, možnosť zavedenia ďaľšej metódy do rozhrania `IAbstractExpression`, radšej využiť Návštevníka

Príbuzné vzory:
- [[Composite]] - syntaktický strom je inštanciou vzoru
- [[Flyweight]] - efektívne zdieľanie listov stromu
- [[Iterator]] - prechádzanie syntaktickým stromom
- [[Visitor]] - správanie každého uzla syntaktického stromu


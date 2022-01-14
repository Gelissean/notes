Stav

- umožnuje objektom zmeniť svoje správanie keď sa zmení vnútorný stav, objekt vyzerá ako by zmenil triedu

- ukázka na TCP/IP - stav established-listen-closed

Stav je vhodné použiť keď:
- správanie objektu je závislé na jeho stave, ktorý sa počas behu programu mení
- operácie majú v kóde veľa vetvení, ktoré sú závislé od stavu objektu
![[state_implementacia.png]]

- centralizuje v sebe špecifické správanie pre konkrétny stav. Je jednoduché rozšírenie objektu o ďaľší stav vytvorením potomka, nie je potrebné zanášať veľa nového kódu
- zmena vnútorného stavu je viac transparentná. Stav sa často mení ako atribút, môže spôsobiť nekonzistentný stav, vzor Stav tomu predchádza, zmena stavu je atomická operácia
- stavy je možné zdieľať cez mušiu váhu

Príbuzné stavy
- [[Flyweight]] - pomocou mušej váhy možno zdieľať stavy
- [[Singleton]] - stavy sú často jedináčikovia

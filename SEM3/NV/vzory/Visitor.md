Návštevník
Behaviorálny vzor

dynamicky možno dopĺňať funkčnosť objektov

Máme kompilátor obsahujúci syntaktické stromy, vykonáva typové kontroly, analýzu kódu, kontrolu inicializácie premenných, generovanie čitateľného kódu

Rozdelenie hierarchie na dve:
1. zapúzdrenie funkčnosti - návštevník
2. Node

![[Visitor_motivacia.png]]

Visitor použiť keď máme v objektovej štruktúre veľa tried, ktoré dokážu robiť veľa.
Rozdeľuje jednotlivé operácie do vlastných tried

![[Visitor_implementacia.png]]
Ak sme mali operácie A,B,C,D, nutno vytvoriť toľko visitorov koľko operácií, a každé prostredie samostatne

Použitím možno jednoducho pridať nové operácie
Jednoducho spojiť súvisiace operácie, kódy sa sprehľadnia
Je kompikované pridať novú triedu typu Element

Visitor nie je viazaný na konkrétnu hierarchiu, je ho možno znovu použiť jednoducho.

Pozor na porušenie zapúzdrenia - nutné zverejniť detaily pomocou getterov

![[visitor_priklad_1.png]]
![[visitor_priklad_2.png]]
![[visitor_priklad_3.png]]

Príbuzné vzory
[[Composite]] - návštevníci môžu využívať aplikáciu operácií ako kompozity
[[Interpreter]] - návštevník môže vykonávať interpretáciu
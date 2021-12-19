Fasáda
Poskytuje jednotné rozhranie množine rozhraní

 - ako v jave - `JOptionPane`
Jedným miestom zastrešiť veľa možných operácií

Tvorí jednoduché rozhranie v rámci komplikovaného systému
Fasáda odstraňuje závislosti medzi realizáciou a klientom
Je možno navrhnúť systém po úrovniach, tvorba fasád, ktoré tvoria rôzne rozhrania na daných úrovniach. Ľahko možno meniť subsystémy iba nahradením fasády.
![[Facade_aplikacia_bez.png]]
![[facade_aplikacia_s.png]]

Fasáda je typicky jedináčik (knižnica).
Fasáda musí poznať prvky subsystému, vie komu čo delegovať.
Odstránením (obídením) fasády sa nesmie rozbiť subsystém.
Fasáda je závislá od prvkoch subsystému, nie naopak

Oddeľuje klientské classy od komponentov systému, nebudú komplexné a cyklické závislosti.
Efektívnejšie možnosti portovania na iný systém a platformu.

Príbuzné vzory:
[[Abstract_factory]] - alternatíva fasády. AF funguje ako agregát, môže fungovať ako fasáda
[[Mediator]] - fasáda je univerzálna, mediátor je úzko zameraný práve na jednu činnosť (komunikáciu)
[[Singleton]] - väčšinou existuje iba jedna fasáda jedného druhu
Mediátor
behaviorálny vzor

Objekt, ktorý zapúzdri vzájomnú komunikáciu veľkej množiny objektov.
Uvoľní previazanosť (objekty o sebe nevedia, nereferencujú sa)
Správu pošlem mediátorovi, viac sa o ňu nestarám, rieši to mediátor

3D scéna, veľké množstvo objektov, kto vie, čo všetko sa musí prekresliť ak sa objekt pohne
"Vinník" povie scéne, nech odkáže ostatným nech sa prerenderujú

Ak zmením objekt muža na ženu vznikne kolónka (checkbox) "tehotná"

Do stredu sa zavádza objekt, ktorý sprostredkuje komunikáciu.

Mediátor sa používa, keď komunikuje veľa objektov. Komunikácia je jasne definovaná
Ak sa znemožní re-use nejakého objektu, využitím mediátora sa odstráni závislosť chceného objektu a umožní sa znova použitie.

![[mediator_implementacia.png]]

Použitím mediátora sa 
- obmedzuje dedičnosť, 
- oddeluje závislosť medzi spolupracovníkmi, 
- zmení sa interakcia m:n na 1:n (jednoduchšie rozšírenie, pochopenie, udržiavanie)
- komplexné pravidlá komunikácie sa koncertuje všetko do mediátora

Príbuzné vzory:
- [[Facade]] - mediátor zastrešuje komunikáciu, fasáda čokolvek
- [[Observer]] - možno spraviť univerzálnejšieho mediátora (zvýšená zložitosť)
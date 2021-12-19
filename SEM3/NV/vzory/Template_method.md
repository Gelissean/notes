šablónová metóda
behaviorálny vzor

Kostra je jednotná, potomkovia upravujú detaily


Varenie čaju:
1. dať vodu do kanvice
2. zapnút kanvicu
3. dať sáčok čaju do hrnčeku
4. počkať kým zovrie voda a zaliať
5. vylúhovať a vybrať sáčok
6. ochutenie

Varenie kávy:
1. voda do kanvice
2. zapnúť kanvicu
3. daj kávu do hrnčeka
4. počkať kým zovrie voda a zaliať
5. ochutiť

Varenie kakaa:
1. mlieko do hrnca
2. zohrejem mlieko
3. nasypať kakao do hrnčeka
4. počkám kým sa mlieko zohreje
5. zalejem kakao
6. rozmiešať

**Šablónová metóda:**
Varenie horúceho nápoja (fajného pitia):
1. Dám zohriať tekutinu (voda, voda, mlieko)
2. nasypem fajnový produkt do hrnčeku (čaj, káva, kakao)
3. počkám kým sa zohreje tekutina (100, 100, 60)
4. zalejem
5. ochutím

Potomok definuje {voda, čaj, 100} / {voda, káva, 100} / {mlieko, kakao, 60}
![[template_method_priklad.png]]

Centralizovanie algoritmu na jedno miesto
Máme pod kontrolou čo potomok môže upravovať
**hook** - v príklade metóda `ochut()`, potomok s ňou môže niečo robiť ale nemusí

![[template_method_implementacia.png]]
Snaha o čo najmenší počet abstraktných metód, ak je počet metód neznámy vhodné využiť [[Command]]

Tvoria sa štyri druhy metód
- neprekryteľné metódy - vlastné metódy
- abstraktné metódy - musia byť prekryté
- továrenské metódy
- **hook** - môžu byť prekryté

Potrebné presne špecifikovať, ktoré operácie sú abstraktné, a ktoré sú *hook*y

Príbuzné metódy
[[Factory_method]] - továrenské metódy sú často volané zo šablónových metód
[[Strategy]] - častu sa šabonové me´tódy využívajú na zmenu časti algoritmu  dedičnosť, stratégie využívajú delegáciu, čím sa môže zmeniť celý algoritmus
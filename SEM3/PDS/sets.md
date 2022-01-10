```sql
Select nazov 
from car_company1 
UNION 
Select nazov 
from car_company2
```
alebo `UNION ALL`
`intersect`

multiset union - vráti všetky výsledky v jednom riadku
- cross join
- intersect
- except

viewy sú uložené v databáze a dajú sa ľahko referencovať

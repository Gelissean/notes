***Monoafinné šifry***
***
**Cézarovská šifra**
- posun o $k$ znakov
- útok hrubou silou - potrebné vyskúšať 25 (abeceda - 1) kľúčov
***
**Afinná šifra**
- dva kľúče
- najskôr sa znak vynásobí prvým kľúčom, potom sa pričíta druhý
- prvý kľúč - 12 možností (nepárne a nie delitele veľkosti abecedy)
- druhý kľúč - 26 možností
***
***Polyafinné šifry***
- využívajú kľúče pozostávajúce z viacerých znakov
***
**Vigenére**
- zvolí sa slovo ako kľúč (napr. HESLO) a to sa postupne aplikuje ako cézerovská šifra (HESLOHESL...)
- na odhalenie dĺžky kľúča sa používa **Kasiského test**
	- V celom text sa kontrolujú opakujúce sa reťazce znakov, dĺžka kľúča je pravdepodobnee najväčším spoločným deliteľom vzdialeností rovnakých výskytov
***
**Hill**
- šifrovacím kľúčom je štvorcová matica (s veľkosťou $n$, ktorá má aj inverznú maticu
- postupnosť $n$ znakov sa šifruje ako vektor násobený šifrovacou maticou
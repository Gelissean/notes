1. Nájdi atribút s najvyššou hodnotou vzájomnej informácie, ktorý sa ešte nepoužíval
2. vytvor uzol následovníka pre každú hodnotu daného atribútu
3. prilož všetky dátové údaje k následovníkovi s tou istou hodnotou sledovaného atribútu
4. ak všetky dátové údaje majú rovnaký výstup, z uzla je list
5. skok na krok 1 ak existuje viac nepoužitých atribútov

**Neusporiadaný strom**
Pri počítaní atribútu sa pracuje iba s hodnotou informácie v danej vetve stromu

**Paralelný výber uzlov**
Na úrovni stromu sa nachádza vždy ten istý atribút, informácia sa počíta cez všetky vetvy stromu
***
- strom je jednoduchý na pochopenie
- jednoduchá implementácia
- model bielej skrinky
- môže byť ťažký na výpočet v prípade veľa nejasných hodnôt
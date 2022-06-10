**Genetický algoritmus**
0. inicializuj dosiaľ najlepšie riešenie ako najlepšie riešenie $y^k$ zo vstupnej populácie
1. ak $t=n$ skončime, inak usporiadajme jedince $y^k$ zo súčasnej populácie vzostupne podľa hodnôt funkcie príslušnosti do $y^{k(i)}$, definuje sa počet nových jedincov ako 0
2. v cykle sa s pravdepodobnosťou $p(r)$ vyberie prvý z hladaných rodičov $y^{k(r)}$
3. v cykle sa s pravdepodobnosťou $p(s)$ vyberie druhý z hladaných rodičov $y^{k(s)}$
4. [[kríženie]]
5. mutácia - náhodná zmena riešenia podľa nejakej náhodnej premennej
6. redukcia populácie, lepší potomok sa zaradí do novej populácie
7. ak nová populácia nie je úplna, vrátiť sa na krok 2, inak sa nová populácia definuje ako súčasná a vráti sa na krok 1

[[Vhodnosť jedinca populácie GA]]
[[selekcia GA]]
[[podmienky zastavenia GA]]
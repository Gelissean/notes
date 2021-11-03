multiset except - rozdiel
multiset union - zjednotenie
multiset intersect - prienik

```sql
declare 
  type t_cisla is table of varchar2(20); 
  cisla_praca t_cisla; 
  cisla_domov t_cisla:=t_cisla('22222'); 
  cisla_komplet t_cisla; 
begin 
  cisla_komplet:=t_cisla(); 
  cisla_komplet.extend(3); 
  cisla_komplet(1):='11111'; 
  cisla_komplet(2):='22222'; 
  cisla_komplet(3):='33333'; 
  cisla_praca:=cisla_komplet multiset except cisla_domov; 
  for i in 1..cisla_praca.count 
  loop 
    dbms_output.put_line(cisla_praca(i)); 
  end loop; 
end; 
/
```

pre vypísanie všetkých prvkov sa používa union, na odstránenie duplikátov sa musí zavolať
`cisla_komplet := set(cisla_komplet)`


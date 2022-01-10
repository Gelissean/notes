row_number, rank, dense_rank
```sql
select 
  row_number() over(order by vysledok) as poradie, 
  meno, priezvisko, 
  extract(hour from vysledok) as hodiny, 
  extract(minute from vysledok) as minuty, 
  extract(second from vysledok) as sekundy 
  from vysledky_tab
```

partition by
```sql
select 
  rank() over(partition by id_sutaze order by vysledok) as poradie, 
  meno, priezvisko, id_sutaze 
  extract(hour from vysledok) as hodiny, 
  extract(minute from vysledok) as minuty, 
  extract(second from vysledok) as sekundy 
  from vysledky_tab
```
best 20%
```sql
select 
  meno, priezvisko, priemer 
  from (
        select 
          meno, priezvisko, priemer, 
          rank() over(order by priemer) rn 
          from ( 
            select 
              meno, priezvisko, 
              priemer(os_cislo) as priemer 
              from priklad_db2.os_udaje 
                join priklad_db2.student using(rod_cislo) 
               ) 
        ) 
  where rn<=(
              select 0.2*count(*) 
                from priklad_db2.student 
            )
```

`row_number() over(order by dat_nastupu NULLS FIRST)`

lag a lead na predchádzajúci a nasledujúci riadok
```sql
select 
  to_char(datum,'HH24'), 
  hodnota, 
  lag(hodnota,1) over(order by datum) 
  from teplota_tab
```

```sql
select * 
from produkty 
order by cena 
fetch first row with ties;
```
\[Only | With ties\]
```sql
select * 
from produkty 
order by cena 
fetch first 2 percent rows only;
```
```sql
select * 
from produkty
order by cena 
offset 2 row
fetch first row only;
```

sum over je rolling sum, nie agregačná ale analytická funkcia
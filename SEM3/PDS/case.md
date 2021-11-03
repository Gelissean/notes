```sql

select meno, priezvisko, cis_predm, 
      case
        when vysledok = 'A' then 1
        when vysledok = 'B' then 1.5
        when vysledok = 'C' then 2
        when vysledok = 'D' then 2.5
        when vysledok = 'E' then 3
        else 4 
        end
      from zap_predmety join student using(os_cislo) join os_udaje using(rod_cislo);
```

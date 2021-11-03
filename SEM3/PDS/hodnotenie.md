rank, dense_rank, row_num
over
```sql
select meno, priezvisko, cis_predm,
        rank() over(order by znamka)
      from 
      (select meno, priezvisko, cis_predm, 
      case
        when vysledok = 'A' then 1
        when vysledok = 'B' then 1.5
        when vysledok = 'C' then 2
        when vysledok = 'D' then 2.5
        when vysledok = 'E' then 3
        else 4 
        end as znamka
        from zap_predmety join student using(os_cislo) join os_udaje using(rod_cislo)
      where cis_predm = 'II12');
```
partition by
```sql
select meno, priezvisko, cis_predm,
        rank() over(partition by skrok order by znamka) as hodnota,
        skrok,
        znamka
      from 
      (select meno, priezvisko, cis_predm, skrok,
      case
        when vysledok = 'A' then 1
        when vysledok = 'B' then 1.5
        when vysledok = 'C' then 2
        when vysledok = 'D' then 2.5
        when vysledok = 'E' then 3
        else 4 
        end as znamka
        from zap_predmety join student using(os_cislo) join os_udaje using(rod_cislo)
      where cis_predm = 'II12');
```
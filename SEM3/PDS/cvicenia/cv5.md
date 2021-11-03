[[JSON]]
[[XML]]
```sql

-- json a xml dokumenty

-- analytika
select meno, priezvisko, priemer, row_number() over (order by priemer)
 from
 (select meno, priezvisko, round(priemer(os_cislo),2) as priemer
  from priklad_db2.os_udaje join priklad_db2.student using (rod_cislo)
   order by 3
   );
   
select meno, priezvisko, priemer, 
   row_number() over (order by priemer) ROW_NUM, 
   rank() over (order by priemer) RANK,
   dense_rank() over (order by priemer) DENSE_RANK
 from
 (select meno, priezvisko, round(priemer(os_cislo),2) as priemer
  from priklad_db2.os_udaje join priklad_db2.student using (rod_cislo)
   order by 3
   );
   
-- 10 najlepsich studentov
select meno, priezvisko, ROW_NUM, RANK, DENSE_RANK
 from
  (select meno, priezvisko, priemer, 
     row_number() over (order by priemer) ROW_NUM, 
     rank() over (order by priemer) RANK,
     dense_rank() over (order by priemer) DENSE_RANK
   from
   (select meno, priezvisko, round(priemer(os_cislo),2) as priemer
    from priklad_db2.os_udaje join priklad_db2.student using (rod_cislo)
     order by 3
     ))
  where rank <= (select 0.1*count(*) from priklad_db2.student);
  
select count(*) from priklad_db2.student;
```

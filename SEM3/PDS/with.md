zabezpečuje modularizáciu
umožnuje viacero pod-dotazov
```sql
WITH 
  student22 as (select zap_predmety .os_cislo , cast(collect ( rec_type (cis_predm , meno ||' ' || priezvisko ) order by cis_predm ) as subject_col ) predmety from zap_predmety join ucitel on (prednasajuci =ucitel .os_cislo ) where zap_predmety .os_cislo =50042 2 group by zap_predmety .os_cislo), 
  student 24 as (select zap_predmety .os_cislo , cast(collect ( rec_type (cis_predm , meno ||' ' || priezvisko ) order by cis_predm ) as subject_col ) predmety from zap_predmety join ucitel on (prednasajuci =ucitel .os_cislo ) where zap_predmety .os_cislo =50042 4 group by zap_predmety .os_cislo ) 
  select * 
    from TABLE 
	  (select student24 .predmety multiset union DISTINCT student22 .predmety as zoznam_predmetov from student24 , student22 ) ;
```

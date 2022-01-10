slúžia na zvyšovanie výkonu jednotlivých dotazov

- implicitné - primárne kľúce, `unique`
- explicitné

na poradí atribútov v indexe záleží, najskôr atribúty v podmienke, potom atribúty v joine, nakoniec atribúty v selecte

typy:
- B+strom
	- pôvodný typ, ROWID a hodnoty stĺpcov vo vyváženom strome
	- žiadne null hodnoty
	- ľahko sa dodržuje unikátnosť kľúča
	- ROWID - id riadku, nepoužívať ako kľúč, menia sa

používanie indexov
- index range scan method
	- všetky požadované dáta sú naindexované
- index unique scan
	- vyhľadáva sa iba naindexovaná unikátna položka
- index fast full scan
	- ak je viac stĺpcov naidexovaných než požadovaných

- index range scan + table access by index rowid
	- ak je potrebné načítať riadok z databázy ako doplnok k indexu
- index unique scan + table access by index rowid
	- ak je potrebné načítať riadok tabuľky iba na základe PK

- table access full
	- číta sa celá tabuľka, nie je vhodný index
	- (hľadanie podľa nenaindexovaného atribútu)

- order by
	- index range scan + table access full

USER_INDEXES
ALL_INDEXES
DBA_INDEXES

```sql
select
  index_name
  from user_indexes
  where table_name = 'STUDENT'
  ```
implicitné indexy majú systémový názov, explicitné určený

**Menežovanie indexov**
alter index *meno* (in)visible
- defaultne nepoužívaný, ale udržiavaný
alter index *meno* unusable
alter index *meno* rebuild
alter index *meno* shrink space
drop index *meno*

```sql
alter index *meno* monitoring usage
select index_name, monitoring, used from v$object_usage
```

  
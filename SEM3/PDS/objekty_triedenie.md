metódy
maximálne jednu metódu
MAP a ORDER

```sql
select id, datum_vykonania, stav, deref(s.auto).print() 
  from stk_tab s; 

select id, datum_vykonania, stav, deref(s.auto).print() 
  from stk_tab s 
  order by deref(auto).cena; 

select id, datum_vykonania, stav, deref(s.auto).print() 
  from stk_tab s 
  order by deref(auto).id;
```

mapovacia funkcia
```sql
map member function tried 
  return integer 
  is 
  begin 
    case 
	  when lower(popis) like 'biel%' then return 0; 
	  when lower(popis) like 'zlt%' then return 1; 
	  when lower(popis) like 'cerven%' then return 2; 
	  when lower(popis) like 'zelen%' then return 3; 
	  when lower(popis) like 'modra%' then return 4; 
	  when lower(popis) like 'sed%' then return 5; 
	  when lower(popis) like 'ciern%' then return 6; 
	  else return 100; 
	end case; 
  end; 
end;
```

metóda order vracia porovnanie, ak je číslo väčšie tak 1, ak menšie tak -1, ak rovné tak 0
[[kolekcie]]
[[bulk_collect]]
[[objekty]]
```sql
-- kolekcie a recordy
-- zopakovane uz v cv1

-- objekty

select * from soc_poistovna.p_osoba;
desc soc_poistovna.p_osoba; -- javi sa ako relacna tabulka

desc soc_poistovna.t_osoba; -- nemame pravo na ten objekt
select value(p) from soc_poistovna.p_osoba p; -- tabulka objektov T_OSOBA


create or replace type t_ziak is object
(
 meno varchar2(20),
 priezvisko varchar2(20)
);
/

declare
 type t_pole is table of t_ziak;
 pole t_pole := t_pole();
 prvok integer;
begin
 for i in (select meno,priezvisko from os_udaje)
 loop
  pole.extend(1);
  pole(pole.last):= t_ziak(i.meno, i.priezvisko);
 end loop;
 
 prvok := pole.first;
 for i in 1 .. pole.count()
 loop
  dbms_output.put_line(pole(prvok).meno);
  prvok := pole.next(prvok);
 end loop;
end;
/

alter type t_ziak add member function vypis return varchar;
--este treba doplnit type body

-- dbms_output.put_line(pole(prvok).vypis());

-- 
select * from soc_poistovna.p_osoba p
 order by value(p);
 -- triedenie podla objektu, T_OSOBA nema order/map
 ```
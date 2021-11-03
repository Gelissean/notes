[[cursor]]
[[kolekcie]]
[[record]]
```sql
-- kurzory a specialne kurzory
select meno, priezvisko 
 from os_udaje
  where rod_cislo = '123456/7890';
  
-- specialny variant kurzora
  
declare
 v_meno os_udaje.meno%type;
 v_priezvisko os_udaje.meno%type;
begin
 select meno,priezvisko into v_meno, v_priezvisko
  from os_udaje
   where rod_cislo = '123456/7890';
exception
 when others then dbms_output.put_line('chyba');
end;
/
-- ked cez sql loader naloadovat mnozstvo dat
-- ak select vrati viac ako 1 zaznam tak exception

declare
 v_meno os_udaje.meno%type;
 v_priezvisko os_udaje.meno%type;
 type t_osoba is record(meno os_udaje.meno%type, priezvisko os_udaje.meno%type);
 type t_kol is table of t_osoba;
-- osoba t_osoba
 osoba t_kol;
begin
 --select meno,priezvisko into v_meno, v_priezvisko
 select meno,priezvisko bulk collect into osoba
  from os_udaje
   where rod_cislo = rod_cislo;
 osoba.delete(3);
 --for i in reverse osoba.first .. osoba.last
 for i in osoba.first .. osoba.last
  loop
   if osoba.exists(i) then
    dbms_output.put_line(i || '-' || osoba(i).meno);
   end if;
  end loop;
exception
 when others then dbms_output.put_line('chyba');
end;
/

-- na teste vypisat dane prvky (od first do last, od 1 do count (next), od zaciatku po koniec, od konca do zaciatku (reverse, prior)

declare
 v_meno os_udaje.meno%type;
 v_priezvisko os_udaje.meno%type;
 type t_osoba is record(meno os_udaje.meno%type, priezvisko os_udaje.meno%type);
 type t_kol is table of t_osoba index  by binary_integer;
 --type t_kol is t_osoba varray(100) of t_osoba;
-- osoba t_osoba
 osoba t_kol;
begin
 --select meno,priezvisko into v_meno, v_priezvisko
 select meno,priezvisko bulk collect into osoba
  from os_udaje
   where rod_cislo = rod_cislo;
 osoba.delete(3);
 -- nad varray nemozeme zavolat .delete()
 --for i in reverse osoba.first .. osoba.last
 for i in osoba.first .. osoba.last
  loop
   if osoba.exists(i) then
    dbms_output.put_line(i || '-' || osoba(i).meno);
   end if;
  end loop;
exception
 when others then dbms_output.put_line('chyba');
end;
/

-- ked je kolekcia prazdna neda sa odkazat na .first ani .last

declare
 v_meno os_udaje.meno%type;
 v_priezvisko os_udaje.meno%type;
 type t_osoba is record(meno os_udaje.meno%type, priezvisko os_udaje.meno%type);
 type t_kol is table of t_osoba;
-- osoba t_osoba
 osoba t_kol;
begin
 --select meno,priezvisko into v_meno, v_priezvisko
 select meno,priezvisko bulk collect into osoba
  from os_udaje
   where rod_cislo = rod_cislo;
 osoba.delete(3);
 --for i in reverse osoba.first .. osoba.last
 for i in osoba.first .. osoba.last
  loop
   if osoba.exists(i) then
    dbms_output.put_line(i || '-' || osoba(i).meno);
   end if;
  end loop;
  osoba := set(osoba); -- na potlacenie duplicity
exception
 when others then dbms_output.put_line('chyba');
end;
/

declare
 type t_pole is table of integer;
 pole1 t_pole := t_pole(11,22,33,44, null);
 pole2 t_pole := t_pole(22,33,44,55, null);
 vysledok t_pole;
begin
 vysledok := pole1 multiset union pole2; -- zjednotenie
 -- vysledok := pole1 multiset intersect pole2; -- prienik, ak je duplicita, bude aj vo vysledku
 vysledok := set(vysledok); -- potlacenie duplicity
 for i in 1 .. vysledok.last
  loop
   dbms_output.put_line(nvl(vysledok(i), -1));
 end loop;
end;
/
-- set je iba pre nested table
-- null hodnoty su rovnake

select meno, priezvisko, nvl(to_char(os_cislo), 'nedefinovane'), rocnik
 --from os_udaje left join student using(rod_cislo)
 from os_udaje left join student on (os_udaje.rod_cislo = student.rod_cislo)
  where rocnik=2 or rocnik is null
  order by os_cislo nulls first;
  
select meno, priezvisko, nvl(to_char(os_cislo), 'nedefinovane'), rocnik
 from os_udaje left join student on (os_udaje.rod_cislo = student.rod_cislo and rocnik = 2)
  order by os_cislo nulls first;
-- spoji tabulku iba ak je rocnik=2
```

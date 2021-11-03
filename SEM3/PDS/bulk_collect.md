```sql
Declare type t_zaznam is record(
 t_meno os_udaje.meno%type,
 t_priezv os_udaje.priezvisko%type,
 t_rod_cislo os_udaje.rod_cislo%type);
 type t_tab is table of t_zaznam;
 tab t_tab;
begin
 select meno, priezvisko, rod_cislo
   bulk collect into tab
  from os_udaje;
 for i in 1 .. tab.count
 loop
 dbms_output.put_line(tab(i).t_rod_cislo);
   end loop;
end;
/
```

možno vytvárať nested table, premenná musí byť typu record, potom cykliť cez for

```sql
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
```
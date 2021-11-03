[[select_into]]

```sql
declare
 v_meno varchar2(20);
 v_priezvisko varchar2(20);
begin
 select meno, priezvisko into v_meno, v_priezvisko
 from os_udaje
 where rod_cislo='841106/3456';
 dbms_output.put_line(v_meno||' '||v_priezvisko);
end;

/ -- Select … into musí vrátiť PRÁVE 1 RIADOK!
```

[[cursor]]
[[bulk_collect]]
[[execute_immediate]]
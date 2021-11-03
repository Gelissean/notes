```sql
declare 
  TYPE T_DeptRec IS RECORD 
    ( 
    id dept.deptno%TYPE, 
    name VARCHAR2(14) DEFAULT 'neznamy', 
    loc VARCHAR2(13):='Zilina' 
    ); 
  dept t_deptrec;
begin 
  dbms_output.put_line(dept.name); 
end;
```

možno využiť typy priamo z tabuľiek

```sql
declare 
  osoba os_udaje%ROWTYPE; 
begin 
  select * into osoba 
    from os_udaje 
	where rod_cislo='841106/3456'; 
  dbms_output.put_line('Meno: ' || osoba.meno);
  dbms_output.put_line('Priezvisko: ' || osoba.priezvisko); 
  dbms_output.put_line('Rodne cislo: ' || osoba.rod_cislo); 
end; 
/
```

v for loopoch je i vždy record
```sql
insert into TAB1 values record
update Tab set row = record
```

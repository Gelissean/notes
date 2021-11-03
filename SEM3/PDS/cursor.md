```sql   
declare cursor cur_st is select rod_cislo, meno, priezvisko, os_cislo
 from os_udaje JOIN student using(rod_cislo);
 rod_cislo varchar2(11);
 meno varchar2(15);
 priezvisko varchar2(15);
 os_cislo integer; 
begin
 open cur_st;
 loop
 fetch cur_st into rod_cislo, meno, priezvisko, os_cislo;
 exit when cur_st%notfound;
 dbms_output.put_line(rpad(rod_cislo, 15) || rpad(meno, 20) || rpad(priezvisko, 20) || os_cislo);
 end loop;
 close cur_st;
end;

/
```

update
```sql
declare
 cursor cur1 is select rod_cislo from student
 for update;
begin
 for i in cur1 loop
 update student
 set ukoncenie=sysdate
 where current of cur1;
 end loop;
end;
 /
```

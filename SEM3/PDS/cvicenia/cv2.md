[[execute_immediate]]
```sql
-- generovanie prikazov
-- chcem dat prava na moje tabulky vsetkym pouzivatelom

--grant select, insert on TABLE_name to matiasko;

select username from dba_users where username='MATIASKO';

declare
 cursor cur_grant is select 'grant select, insert on ' || table_name || ' to matiasko' as prikaz
                      from tabs;
begin
 for i in cur_grant
 loop
  dbms_output.put_line(i.prikaz);
  -- execute immediate(i.prikaz);
  end loop;
end;
/
```
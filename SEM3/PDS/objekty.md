```sql
CREATE [OR REPLACE] TYPE type_name 
[AUTHID {CURRENT_USER | DEFINER}] { {IS | AS} OBJECT | UNDER supertype_name } 
( 
attribute_name datatype[, attribute_name datatype]...
[{MAP | ORDER} MEMBER function_spec,]
[{FINAL| NOT FINAL} MEMBER function_spec,] 
[{INSTANTIABLE| NOT INSTANTIABLE} MEMBER function_spec,] 
[{MEMBER | STATIC} {subprogram_spec | call_spec}
[, {MEMBER | STATIC} {subprogram_spec | call_spec}]...] 
) 
[{FINAL| NOT FINAL}] 
[{INSTANTIABLE| NOT INSTANTIABLE}];

[CREATE [OR REPLACE] TYPE BODY type_name 
{IS | AS} 
{{MAP | ORDER} MEMBER function_body;
| {MEMBER | STATIC} {subprogram_body | call_spec};} 
[{MEMBER | STATIC} {subprogram_body | call_spec};]... 
END;
```

doplnenie tela objektov
```sql
CREATE TYPE BODY 
  definicia_funkcii_objektu 
  AS 
  MEMBER FUNCTION fcia1.... 
  BEGIN 
    RETURN ... 
  END fcia1; 
  MEMBER FUNCTION fcia2.... 
  ... 
END; -- koniec tela fcie
```

tvorba objektu
```sql
create or replace type t_vozidlo as object 
( 
  id integer,
  pocet_kolies integer, 
  cena integer, 
  nazov varchar2(30), 
  NOT INSTANTIABLE MEMBER FUNCTION data_ok return boolean, 
  MEMBER FUNCTION print return varchar2 
 ) 
 NOT INSTANTIABLE NOT FINAL;
/
```
dedičnosť cez `meno under t_objekt`

možno vytvoriť tabuľky cez 
`create table auta_tab of t_auto`
`insert into auta_tab values (new t_auto(...));`

pre získanie objektu z tabuľky nutné použiť value
`select value(p) from auta_tab p;`

definovat predkovu triedu pomocou `NOT FINAL`
abstraktnu pomocou `NOT INSTANTIABLE`


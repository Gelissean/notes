```sql
Create table books_json 
(
  id integer, 
  doc CLOB, 
  constraint valid_json_cons CHECK (doc is json) 
);

insert into books_json (doc) values 
(
  '{
    "Title" : "Temporálne databázy", 
	"Author " : "Michal Kvet", 
	"Type" : "monography", 
	"Detail" : 
	  {
	    "Publisher" : "EDIS", 
		"Publication_year " : 2020 , 
		"ISBN" : "978 -80 -554 -1662 - 5", 
		"Language " : "Slovak", 
		"Pages " : 320 , 
		"Price " : 21 
	  } 
   } ' 
);

select b.doc 
  from books_json b;
```
všetky prvky sú case-sensitive, je potrebné písať prefix "b. ..."
```sql
select b.doc.Title 
  from books_json b 
    where lower(b.doc.Title) like '%data%';
```
b.doc is JSON 
$ expresses root element (dot notation is used)
At the end of the specification, "?" symbol is present 
@ expresses current position 
@.Title – expresses element on the core layer 
Condition is expressed by the equality sign used twice 
String is encapsulated by the quotation marks
AND is &&
funkcie:
- json_value - musí byť skalárna hodnota (bool vracia string)
```sql
select json_value(b.doc, '$.Title') 
  from books_json b
```
- json_query
- json_table - vytvorí tabuľku z JSON dát
```sql
select jt.nazov_knihy, jt.kategoria 
  from books_json b, json_table(b.doc, '$' columns(Nazov_knihy varchar2(50) path Title, Kategoria varchar2(30) path Type)) jt;
```
možno definovať samotné stĺpce
`columns(vydavatelstvo varchar2(30) path Detail.Publisher)`

podmienky:
- json_exists
```sql
select b.doc.Title 
  from books_json b 
    where json_exists(b.doc, '$?(@.Title=="Temporálne databázy")');
```
- is json,
- is not json
- json_textcontains

generovanie JSONu:
- json_object
```sql
select json_object(
  'name' value meno || ' ' || priezvisko, 
  'student_id' value os_cislo ABSENT ON NULL) 
    from os_udaje left join student using(rod_cislo);
```
- json_array - agregačná funkcia, potrebuje group by
```sql
select json_object('name' value meno || ' ' || priezvisko, 
                   'student_id' value os_cislo, 
				   'student_info' value 
				     json_object('class' value rocnik, 
					             'st_group' value st_skupina), 
					'reg_subjects' value 
					  json_array(min(vysledok), max(vysledok))) 
  from os_udaje 
  join student using(rod_cislo) 
  join zap_predmety using(os_cislo) 
    group by meno, priezvisko, os_cislo, rocnik, st_skupina;
```
- json_objectagg
```sql
select os_cislo, 
  json_objectagg('predmet' value cis_predm||‘-'||vysledok) 
  from zap_predmety
  group by os_cislo;
```
- json_arrayagg
```sql
select json_object('name' value meno || ' ' || priezvisko, 
                   'student_id' value os_cislo, 
				   'reg_subjects' value 
				     json_arrayagg(cis_predm)) 
  from os_udaje 
  join student using(rod_cislo) 
  join zap_predmety using(os_cislo) 
    group by meno, priezvisko, os_cislo;
```

na vkladanie slúži:
```sql
insert into books_json (doc) 
  values ( 
	'{ 
	"Title" : "APEX", 
	"Author" : ["Michal Kvet", "Karol Matiasko"], 
	"Type" : "studying literature", 
	"Detail" : 
	  { 
	    "Publisher" : "EDIS", 
		"Publication_year " : 2020 , 
		"ISBN" : "xxx", 
		"Language" : "Slovak", 
		"Pages" : 320 , 
		"Price" : 21 
	  } 
	 }' 
  ) 
;
```
uprava JSON dokumentov pomocou json_mergepath
```sql
select json_mergepatch(b.doc, 
                       '{"Detail": 
					     { 
						   "Publisher": "Oracle Press", 
						   "Publication_year": 2021, 
						   "ISBN": "xxx", 
						   "Language": "English", 
						   "Pages": 520, 
						   "Price": 50 
						 } 
					   }'
					  ) 
  from books_json b 
    where b.doc.Title='APEX';
	
update books_json b 
  set b.doc=json_mergepatch(b.doc, 
                            '{"Detail": 
							  { 
							    "Publisher": "Oracle Press", 
							"Publication_year": 2021, 
								"ISBN": "xxx", 
								"Language": "English", 
								"Pages": 520, 
								"Price": 50 
							  } 
							}'
						   ) 
    where b.doc.Title='APEX';
```

na export sa serializuje
```sql
select json_serialize(b.doc pretty) 
  from books_json b
    where b.doc.Title='APEX';```
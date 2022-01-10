```sql
insert into studenti_xml values
 (XMLType('
 <student oc="500423">
   <meno>Jozef</meno>
   <priezv>Brna</priezv>
   <rod_cislo>831002/8463</rod_cislo>
   <info>
     <skupina>5ZS000</skupina>
     <odb>Informacne systemy</odb>
     <zam>Informacno-komunikacne systemy</zam>
     <stav></stav>
   </info>
 </student>

 '));
```
na select 
```sql
select value(s) from studenti_xml s;
select object_value from studenti_xml;
select s.getClobVal() from studenti_xml s;
```

funkcia `...where EXISTSNODE(xml_type, xml_path) = 1`
funkcia `select EXTRACT(value(s), '/student/info') from studenti_xml s;`
alebo `extractvalue`, táto ale potrebuje vrátiť hodnotu atribútu
```sql
select XMLRoot(EXTRACT(value(s), '/student/info'), version '1.0')
 from studenti_xml s;

select value(s)
 from studenti_xml s
 where EXTRACTVALUE(value(s),'/student/@oc')=500423;
```

dátový typ `xmltype`
```sql   
Select extract(p.data, '/student/info')
 from osoby_xml p
 where extractValue(p.data, '/student/meno')='Jozef';
```

v prípade, že sa v objekte nachádza pole, treba prvok adresovať cez atribút
```sql
Select extract(p.data, '/student/info[@oc="12345"]')
 from osoby_xml p
```

update elementu
```sql
update studenti_xml s
 set value(s) = UpdateXML(value(s),
 '/student/priezv/text()', 'Stara',
 '/student/rod_cislo/text()', '936006/1234')
 where ExtractValue(value(s), 'student/priezv') = 'Nova';
 
update studenti_xml s
 set value(s) = UpdateXML(value(s), '/student/info',
    XMLType('
       <info>
       <skupina>5ZSS18</skupina>
       <odb>Informacne systemy</odb>
       <zam>IKS</zam>
       </info>
       '))
 where ExtractValue(value(s), '/student/priezv') = 'Stara';

update studenti_xml s
 set value(s) = UpdateXML(value(s), '/student/@oc', '11111')
 where ExtractValue(value(s), '/student/priezv') = 'Stara';
```
XML funkcie:
- XMLRoot() `xmlroot(hodnota, version '1.0')`
- XMLElement() - vytvorí element
```sql
select XMLElement("krstne_meno",meno),
 XMLElement("priezvisko", priezvisko)
 from os_udaje
 where meno like 'M%';
```
- XMLAttributes - vytvorí atribút elementu
```sql
XMLElement("osoba",
 XMLAttributes(rod_cislo as "rc",
 os_cislo as "oc"),
```
- XMLForest() - vytvorí pole
```sql
XMLForest(meno as "meno",
 priezvisko as "priezvisko",
 os_cislo as "oc",
 st_skupina as "skupina",
 to_char(dat_zapisu, 'DD.MM.YYYY') as "zapis“
  )
```
- XMLAgg() - agregačná funkcia, potrebuje group by
- XMLConcat()
- XMLComment()
- XMLSequence()
- XMLColAttVal()

prolog - verzia
kódovanie
verzia, znakove sady
dokument

správnosť 
- dobre formulovaný - vyhovuje pravidlám pre tvorbu XML
- správny (validný) - musí spĺňať užívateľom stanovenú XML schému (dtd, xsd, ...)

registrácia schémy `dbms_xmlschema.registerSchema(url,schema_dokument, TRUE, TRUE, FALSE, FALSE);`

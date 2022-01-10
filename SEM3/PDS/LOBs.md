typy:
- CLOB - character LOB
- NCLOB - multibyte character set
- BLOB - binary files
- BFILE
	- do 128tb
	- iba externe
	- hodnota null, locator drží ukazateľ

typy:
- basic file
- secure file
	- lepší výkon, bezpečnosť
	- kompresia
	- enkrypcia
	- de-duplikácia
		- súbory schované za bezpečnostný hash, môže byť viacero súborov zlinkovaných

typy:
- internal
	- iba v databáze, musia mať offsety a dĺžku
- external
	- veľké súbory, ktoré drží OS

```sql
Create directory DEMO_DIR as '/home/matiasko/data_load';
Grant read, write on directory DEMO_DIR to kvet1;

DECLARE
  v_source_clob BFILE := BFILENAME(‘DEMO_DIR’, ‘Textak.txt’);
  v_source_blob BFILE := BFILENAME(‘DEMO_DIR’, ‘Fotka.jpg’);
  v_size_clob integer;
  v_size_blob integer;
  v_clob CLOB := EMPTY_CLOB();
  v_blob BLOB := EMPTY_BLOB(); 
BEGIN 
  DBMS_LOB.OPEN(v_source_clob, DBMS_LOB.LOB_READONLY);
  DBMS_LOB.OPEN(v_source_blob, DBMS_LOB.LOB_READONLY); 
  v_size_clob := DBMS_LOB.GETLENGTH(v_source_clob);
  v_size_blob := DBMS_LOB.GETLENGTH(v_source_blob); 
  INSERT INTO Lob_tab(id, text, fotka) values(5, EMPTY_CLOB(), EMPTY_BLOB()) returning text, fotka into v_clob, v_blob;
  DBMS_LOB.LOADFROMFILE(v_clob, v_source_clob, v_size_clob);
  DBMS_LOB.LOADFROMFILE(v_blob, v_source_blob, v_size_blob);
  DBMS_LOB.CLOSE(v_source_clob); 
  DBMS_LOB.CLOSE(v_source_blob);
  UPDATE Lob_tab SET text=v_clob, fotka =v_blob WHERE ID=5; 
END; 
/
```

do clobu možno ukladať priamo text

```sql
DECLARE
  v_clob CLOB;
  v_write_txt varchar2(100) := 'Object Technologies is difficult subject. ';
  v_append_txt varchar2(100) := 'Advanced Data Structures is more difficult subject'; 
  v_buffer_amount integer;
  v_offset integer;
  BEGIN select text into v_clob from Lob_tab where id=2 FOR UPDATE;
  v_offset := DBMS_LOB.GETLENGTH(v_clob) +3; 
  v_buffer_amount := LENGTH(v_write_txt); 
  DBMS_LOB.WRITE(v_clob, v_buffer_amount, v_offset, v_write_txt);
  v_buffer_amount := LENGTH(v_append_txt); 
  DBMS_LOB.WRITEAPPEND(v_clob, v_buffer_amount, v_append_txt);
END; 
/ 
COMMIT;
```

na prepisovanie LOBov je potrebné ich uzamknúť keď sa pri selecte použije klauzula `FOR UPDATE`
LOB nesmie byť primárny kľúč
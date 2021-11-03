index by table `index by binary_integer`
nested table
varray - má maximálnu dĺžku

```sql
pole.delete(i) --je možné všade okrem varray

declare 
  type t_student_kol is table of student%rowtype; 
  student_kol t_student_kol; 
begin 
  student_kol:=t_student_kol(); 
  for i in (select * from student) 
  loop 
    student_kol.extend(); 
	student_kol(student_kol.last):=i; 
  end loop;
  --vypis 
  for i in 1..student_kol.last 
  loop 
    if student_kol.exists(i) 
	  then dbms_output.put_line(rpad(student_kol(i).os_cislo, 10) || rpad(student_kol(i).rod_cislo, 15) || rpad(student_kol(i).rocnik, 3)); 
	end if; 
  end loop; 
end; 
/

pole:=t_pole(1=>'prvy text', 
             5=>'piaty text', 
			 10=>'desiaty text' 
			 );
			 
type t_student_kol is varray(100) of student%rowtype;
```

metódy
exists, count, limit, first,last, prior, next, extend, trim, delete

```sql
declare 
  type t_student_kol is table of student%rowtype;
  student_kol t_student_kol;
begin 
  select * bulk collect into student_kol from student;
```

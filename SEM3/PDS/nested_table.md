```sql
insert into table
(select c.prvky from cisla_tab c where id=2)
values(10)
```
```sql
delete from table(
  select c.prvky from cisla_tab c where id=2
) nest 
where nest.column_value=10;
```


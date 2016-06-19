### inserting into database

syntax
` insert into <table> values (<value 1>,<value 2>, ...); `

```
insert into books values(16, "1984", "Goege Orwell","fiction", 1949)

```

syntax 

` insert into <table>(<column-1>,<column-2>) values (<value 1>,<value 2>, ...); `



```
insert into books(id,year,name,genre,year_published) values(16, "1984", "Goege Orwell","fiction", 1949)

```

### Updating all rows in database

syntax 

` Update <table> Set <column> = <value>; `



```
update patrons set last_name="Anonymous", first_name="Anonymous" where email="jj@gmail.com";

```


### condition examples 


`<column> <operator> <value>`

`<column> IN (<value 1>, <value 2>, ...)`

`<column> BETWEEN <lower  value> and <larger value>`

`<column> like <pattern>` 



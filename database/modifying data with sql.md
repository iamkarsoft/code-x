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


### deleting  data 

syntax 

`delete from table;`


```
delete from patrons;
```

- deleting from rows 

```
delete from books where title like "Harry Potter";

	//or

delete from patrons where id=4; 

```


### Handling error when manipulating data

removing autocommit  on running queries

- transactions


```
Begin Transactions or Begin // removing autocommit


Commit; // ending transactions
```

- Rolling back from transactions 

undoing the querry runned 

```
Rollback;
``` 

### Object-Relational Mapping

performs Crud operations with a language other than SQL.

 Benefits
 - handle transactions
 - using singles under the hood 

 
##### Ordering results

`select <columns> from <table> order by <column>;`


- ascending


```
select <columns> from <table> order by <column> ASC;
```

- descending 


```
 select <columns> from <table> order by <column> DESC, <column> DESC;
```

##### Limiting and paging results


```
select * from <table> Limit <# of rows>;


select * from <table> where <condition> Limit <# of rows>;

```
 

##### Creating a multi page result with offset

`select * from <table> limit <# of rows> offset <skipped rows>;` or a short hand 
`select * from <table> limit <skipped rows>, <# of rows>;`

```
select * from orders LIMIT 50 OFFSET 50;

```

##### Functions 

- keywords data presented unaltered
- operators performs comparisons and simple manipulation
- functions presends data differently through manipulation

syntax

`<name>(<value or column>)`

i.e `UPPER("Kofi Ramos");`

- adding text and columns together 

```
select first_name as "First Name", last_name as "Last Name", email as "Email", phone as "Phone" from customers;
```

- using concatenation to combine columns

```
select first_name || last_name as "Full name" from customers;
``` 

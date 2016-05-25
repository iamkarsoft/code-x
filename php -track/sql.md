
### Uses of Data and Database 

Databases helps us store data, it is used all around the world to store any kind of infomormation from name of books, email addresses, product names and images etc

### SQL (structured query languages)
the universal language of databases

### Schema

schema determines how databased is designed and how to access the data 

### Data types

data types  determine the values to be stored 


- text 
- Numeric
- Date 


##### Syntax

the vocabulary and grammatical structure of a  programming language

- query or statement

```
SELECT * FROM books; // this select all from the table books;
SELECT * FROM <table name>;

```
##### Retrieving a certain limit of data 

- syntax 

```
SELECT <column name> FROM <table name>; 

```

- examples 

```
SELECT email FROM users;
SELECT first_name, email FROM users;
SELECT name FROM products;
SELECT zip_code FROM addresses;
```
```
select id, username, password, first_name,last_name from users
```
###### Renaming results as we choose
You're not restricted to displaying the column names from the table at the top of your results. You can specify your own names for result sets.

- syntax

```
SELECT <column name> AS <alias> FROM <table name>;
SELECT <column name> <alias> FROM <table name>;
```

- examples

```
SELECT username AS Username, first_name AS "First Name" FROM users;
SELECT title AS Title, year AS "Year Released" FROM movies;
SELECT name AS Name, description AS Description, price AS "Current Price" FROM products;
SELECT name Name, description Description, price "Current Price" FROM products;

```

- the where clause

The real power of SQL comes from filtering rows of information. You've filtered columns, not you're going to filter rows.

```
SELECT <columns> FROM <table> WHERE <condition>;

SELECT <columns> FROM <table> WHERE <condition>=<valute>;

SELECT <columns> FROM <table> WHERE <condition>!=<valute>;

```

##### Filtering by comparing

- equality (=)
- inequality (!=)
- less than (<)
- more than (>)
- greater than or equal to (>=)
- less than or equal to (<=)


##### COnditions 
 selecting with coditions and & or 

```
SELECT <columns> FROM <table> WHERE <condition 1> AND <condition 2> ...;
SELECT <columns> FROM <table> WHERE <condition 1> OR <condition 2> ...;
```

example 

```
select * from results where away_team="Hessle" and away_score > 18;
```

##### Date types

```
SELECT first_name, last_name FROM users WHERE date_of_birth < '1998-12-01';
SELECT title AS "Book Title", author AS Author FROM books WHERE year_released <= 2015;
SELECT name, description FROM products WHERE price > 9.99;
SELECT title FROM movies WHERE release_year >= 2000;
```

##### Searching within a set of values 

```
SELECT <columns> FROM <table> WHERE <column> IN (<value 1>, <value 2>, ...);
```

examples 

```
SELECT name FROM islands WHERE id IN (4, 8, 15, 16, 23, 42);
SELECT * FROM products WHERE category IN ("eBooks", "Books", "Comics");
SELECT title FROM courses WHERE topic IN ("JavaScript", "Databases", "CSS");
SELECT * FROM campaigns WHERE medium IN ("email", "blog", "ppc");

//opposite 

SELECT answer FROM answers WHERE id IN (7, 42);
SELECT * FROM products WHERE category NOT IN ("Electronics");
SELECT title FROM courses WHERE topic NOT IN ("SQL", "NoSQL");
```

- Searching Within a Range of Values

```
SELECT <columns> FROM <table> WHERE <column> BETWEEN <lesser value> AND <greater value>;

```

Examples:

```
SELECT * FROM movies WHERE release_year BETWEEN 2000 AND 2010;
SELECT name, description FROM products WHERE price BETWEEN 9.99 AND 19.99;
SELECT name, appointment_date FROM appointments WHERE appointment_date BETWEEN "2015-01-01" AND "2015-01-07";
```


##### Data that matches 
 syntax 
 
 ```
 SELECT <columns> FROM <table> WHERE <column> LIKE <pattern>;
 ```

example 

```
SELECT title FROM books WHERE title LIKE "Harry Potter%Fire";
SELECT title FROM movies WHERE title LIKE "Alien%";
SELECT * FROM contacts WHERE first_name LIKE "%drew";
SELECT * FROM books WHERE title LIKE "%Brief History%";
```











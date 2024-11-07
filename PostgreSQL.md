# Basic Commands
## CREATE TABLE
### Syntax
```PostgreSQL
CREATE TABLE person (
	id BIGSERIAL NOT NULL PRIMARY KEY,
	first_name VARCHAR(50) NOT NULL,
	last_name VARCHAR(50) NOT NULL,
	date_of_birth date NOT NULL,
);
```
## DROP TABLE
### Syntax
```PostgreSQL
DROP TABLE person;
```
## INSERT INTO
### Syntax
```PostgreSQL
INSERT INTO person ( first_name, last_name)
VALUES ( 'Sridhar', 'Kedlaya');
```
## SELECT FROM
### Syntax
```PostgreSQL
SELECT * FROM person;
SELECT first_name FROM person;
```

## ORDER BY
### Syntax
```PostgreSQL
SELECT * FROM person ORDER BY first_name;
SELECT * FROM person ORDER BY first_name ASC;
SELECT * FROM person ORDER BY first_name DESC;
```

## DISTINCT
### Syntax
```PostgreSQL
SELECT DISTINCT country_of_birth FROM person ORDER BY country_of_birth ASC;
```

## WHERE Clause
### Syntax
```PostgreSQL
SELECT * FROM person WHERE gender = 'Female';
SELECT * FROM person WHERE gender = 'Male' AND country_of_origin = 'Loen Kingdom';
```
## Comparison Operators
### Syntax
```PostgreSQL
SELECT 1 = 1;
SELECT 1 < 2;
SELECT 1 >= 3;
SELECT "Sridhar" <> "Klein"
```
## LIMIT , OFFSET and FETCH
### Syntax
```PostgreSQL
SELECT * FROM person LIMIT 10;
SELECT * FROM person OFFSET 5 LIMIT 15;
SELECT * FROM person OFFSET 5 FETCH FIRST 5 ROW ONLY; /* Original Sql Syntax*/
```
## IN
### Syntax
```PostgreSQL
SELECT * FROM person WHERE country_of_birth IN ('Loen Kingdom', 'Intis Republic', 'Feysac Empire');
```
## BETWEEN
### Syntax
```PostgreSQL
SELECT * FROM person WHERE date_of_birth BETWEEN DATA '2000-01-01' AND '2015-01-01'
```
## LIKE and ILIKE
### Syntax
```PostgreSQL
SELECT * FROM person WHERE email LIKE '%.com';
SELECT * FROM person WHERE email LIKE '%@bloomberg.com';
SELECT * FROM person WHERE email LIKE '%@google.%';
SELECT * FROM person WHERE email LIKE '______@%';
SELECT * FROM person WHERE email LIKE '___o__@%';
SELECT * FROM person WHERE country_of_birth ILIKE 'p%';
```
## GROUP BY
### COUNT()
`COUNT(*)` counts all rows
`COUNT(Column_Name)` counts only the non null rows in `Column_Name`
### Syntax
```PostgreSQL
SELECT country_of_birth, COUNT(*) from person GROUP BY country_of_birth;
```
## HAVING
Used to setup conditionals after aggregation where as `WHERE`  is used to set up conditionals before aggregation.
The Where clause acts as a **pre filter** where as Having as a **post filter.**
### Syntax
```PostgreSQL
SELECT country_of_birth, COUNT(*) from person GROUP BY country_of_birth HAVING country_of_birth IN ('Loen Kingdom', 'Intis Republic', 'Feysac Empire');
```

# Arithmetic Commands
## SUM
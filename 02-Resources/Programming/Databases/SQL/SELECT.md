---
tags:
  - SQL
---
# SELECT
- **SELECT** is one of the most important keywords in SQL.
```SQL
SELECT <column_name(s)>
FROM <table_name>;
```

- All statements must include a **FROM** clause.
- A basic **SELECT** statement only includes a **FROM** clause

### Example
```SQL
SELECT salary FROM employess WHERE last_name like 'Smith';
```
>[! note] Returns salaries of all employees with last name "Smith"

>[! tip] You can use the wild card selector, asterisk symbol, to quickly display all columns and rows in a table

```SQL
SELECT * FROM countries
```
> [! note] Displays all columns and rows from the Countries table

```SQL
SELECT * 
FROM mary.students
```
>[!note] Selecting elements from a table not owned by the user using a prefix. Access must be granted

You can also display all, or just the ones you need, of the columns in a table by listing them individually.
```SQL
SELECT country_id, country_name, region_id FROM countries
```

## Order of Execution
1. FROM
2. WHERE
3. SELECT
4. ORDER BY




---
tags:
  - SQL
---
# Simple View
- The subquery dervies data from only one table and it does not contain a join function or any group functions.
- DML operations affecting the base table could possbily be performed through the view.
- Column names in the SELECT statment can have aliases.
- It's possible to create a view wheter or not the base tables exist
	- Adding the word <code>FORCE</code> to the <code>CREATE VIEW</code> statement creates the view.

### Example
```SQL
CREATE OR REPLACE VIEW view_euro_countires
AS SELECT country_id, country_name, capitol
	FROM wf_countries
	WHERE location LIKE '%Europe';
```
>[!note] Simple view creation

```SQL
CREATE OR REPLACE VIEW view_euro_countires
AS SELECT country_id AS "ID", country_name AS "COUNTRY", capitol AS "Capitol City"
	FROM wf_countries
	WHERE location LIKE '%Europe';
```
>[!note] View creation with aliases *after* the CREATE VIEW statement

```SQL
CREATE OR REPLACE VIEW view_euro_countires("ID", "Country", "Capitol City")
AS SELECT country_id, country_name, capitol
	FROM wf_countries
	WHERE location LIKE '%Europe';
```
>[!note] View creation with aliases *before* the SELECT statment

## Querying From USER_VIEWS
```SQL
SELECT view_name, text
FROM user_views  where view_name='<view_name>';
```





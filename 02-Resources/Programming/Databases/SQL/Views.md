---
tags:
  - SQL
---

# Views
- Like a table, a **view** is a database object
- The tables which a view is based are called *base tables*
- They are not "real" tables.
- Logical representations of existing tables or of another view
- Contain no data of their own.

>[!tip] A window through which data from tables can viewed or changed.

## Syntax
```SQL
CREATE [OR REPLACE] [FORCE| NOFORCE] VIEW viewp[(alias [,alias]...)] AS subquery
[WITH CHECK OPTION [CONSTRAINT constraint]]
[WITH READ ONLY [CONSTRAINT constraint]];
```

| Keyword           | Description                                                                                                                             |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| OR REPLACE        | Re-creates the view if it already exists                                                                                                |
| FORCE             | Creates the view whether or not the base tables exist                                                                                   |
| NOFORCE           | Creates the view only if the base table exists(default)                                                                                 |
| view_name         | Specifies the name of the view                                                                                                          |
| alias             | Specifies a name for each expression selected by the view's query                                                                       |
| subquery          | Is a complete SELECT statement. You can use aliases for the columns in the SELECT list. The subquery can contain complex SELECT syntax. |
| WITH CHECK OPTION | Specifies that rows remain accessbile to the view after insert or update operations                                                     |
| CONSTRAINT        | Is the name assigned to the CHECK OPTION constraint                                                                                     |
| WITH READ ONLY    | Ensures that no DML operations can be performed on this view.                                                                                                                                        |

## Why Use Views?
- Restrict access to base table data 
	- The view can display selective columns from the table
- Can be used to reduce the complexity of executing queries based on more complicaed SELECT statements
- Can be used to retrieve data from several tables
	- Provides data independence for users.
- Users can view the same data in different ways.
- Provide groups of users with access to data according to their permissions or criteria.

## Guidlines
- The subquery  that defines the view can contain complex SELECT syntax
- The subquery that defines the view should not contain an [[ORDER BY]] clause.
	- This is only specifed when retreiving the data
- You can use OR REPLACE option to change the definition of the view without having to drop it.
- Aliases can be used for the column names in the subquery.

## Features
- Two classifications of views:
	- Simple
	- Complex
| Feature                                                            | Simple Views | Complex Views |
| ------------------------------------------------------------------ | ------------ | ------------- |
| Number of tables used to derive data                               | One          | One or more   |
| Can contain functions                                              | No           | Yes           |
| Can contain groups of data                                         | NO           | Yes           |
| Can perform DML operations (INSERT, UPDATE, DELETE) through a view | Yes          | Not always              |

### Example
```SQL
CREATE VIEW view_employees
AS SELECT employee_id, first_name, last_name, email
	FROM employees
	WHERE employee_id BETWEEN 100 and 124;
```

```SQL
SELECT * FROM view_employees;
```

```SQL
CREATE OR REPLACE VIEW view_euro_countires
AS SELECT country_id, region_id, country_name, capitol
	FROM wf_countries
	WHERE location LIKE '%Europe';
```

```SQL
SELECT * FROM view_euro_countires
ORDER BY country_name;
```





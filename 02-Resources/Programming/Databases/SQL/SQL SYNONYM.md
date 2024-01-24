---
tags:
  - SQL
---

---
Created: [[04-23-2023]]
tags: 
---
# SQL SYNONYM
- A word or expression that is an accepted substitue for another word.
- Used to simplify access to objects by creating another name for the object
- Make referring to a table owned by another user easier and shorten length object names.
	- Can be be public or private
- Eliminates the need to qualify the object name with the schema and provides you with an alternative name for a table, view, sequence or other object.

>[!tip] Useful with lengthy object names, such as views

- Guidlines:
	- The object cannot be contained in a package
	- A private synonym name must be distinct from all other objects owned by the same user.
- **Prerequisities**
	- To create a private synonym in your own schema, you must have <code>CREATE SYNONYM</code> privilege
	- To create a private synonym in another user's schema, you need <code>CREATE ANY SNYONYM</code> privilege
	- To create a PUBLIC synonym, you need <code>CREATE PULBIC SYNONYM</code> privilege

- The existence of synonyms can be confirmed by querying the <code>USER_SYNONYMS</code> data dictionary view.

## Syntax
```SQL
CREAT [PUBLIC] SYNONYM synonym
FOR object;
```

## Remove a Synonym
```SQL
DROP [PUBLIC] SYNONYM name_of_synonym
```

### Examples
```SQL
SELECT * FROM lion.sales

CREATE PUBLIC SYNONYM sales FOR lion.sales

SELECT * FROM sales
```
>[!note] Suppose you have a table called sales in the schema owned by the user lion and you granted the SELECT privilege for the sales table to the PUBLIC. A PUBLIC synonym would simplify the query.
>

---
tags:
  - college
---

# Final Project

## Create Tables 
- [x] Customers
- [x] Movies
- [x] Media
- [x] Rental History
- [x] Actors
- [x] Star Billings

## Add Constraints to Tables
- [x] Customers
- [x] Movies
- [x] Media
- [x] Rental History
- [x] Actors
- [x] Star Billings
- [ ] Verify queries from data dictionary
```SQL
SELECT constraints_name, table_name, constraint_type, status
FROM USER_CONSTRAINTS
WHERE table_name = '<table_name>';
```

## Creating and Managing Views
- [ ] Create a view called TITLE_UNAVAIL to show movie titles and media_id of media not returned yet.
>[! warning] This view should not allow DML operations
- Select title_id from movies table
- select media_id from media table


## Working with Sequences (indexes and Synonyms)
- Create the following sequences to be used for primary key values:
- [x] Use a sequence to generate PKs for CUSTOMER_ID in CUSTOMERS table
	- *Begin at 101 and increment by 1*
- [x] generate PKs for TITLE_ID in MOVIES table
	- *Begin at 1 and increment by 1*
- [x] generate PKs for MEDIA_ID in MEDIA table
	- *Begin at 92 and increment by 1*
- [x] generate PKs for ACTOR_ID ini ACTOR table
	- *Begin at 1001 and increment by 1*
- [ ] Add data to the tables 
	- [x] Customers
	- [x] Movies
	- [x] Media
	- [x] Rental History
	- [x] Actors
	- [x] Star Billings
- [ ] Create an index on the last_name column of the CUSTOMERS table.
- [ ] Create a synonym called TO for the TITLE_UNAVAIL view.

[Cheat Sheet](https://hemantrohtak.blogspot.com/2016/11/)
![[OracleFlix_SQL_Project_Tables 1.pdf]]
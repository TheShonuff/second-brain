---
tags:
  - SQL
---
# Database Links
- A pointer that defines a one-way communication path from one Oracle database to another database.
	- IF local users on database B want to access data on database A, they must define a link that is stored in the data dictionary of Database B
- Defined as an entry in a data dictionary table.
- To access the link, you must be connect to the local database that contains the data dictionary entry.
- For the connection to occur, each database in the distributed system must have a unique global database name.

### Example
```SQL
CREATE PUBLIC SYNONYM HQ_EMP
	FOR emp@HQ.ACME.COM;
```


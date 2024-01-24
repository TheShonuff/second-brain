---
tags:
  - SQL
---
# Data Dictionary Views
- Views are divided into three groups:
	- USER
	- ALL
	- DBA|

## User
*Tuples in the USER views contain information about ojects owned by the account performing the SQL query (current user)*

| View              | Description                                                                                          |
| ----------------- | ---------------------------------------------------------------------------------------------------- |
| USER_TABLES       | All tables with their name, number of columns, storage information, statistical infromation **TABS** |
| USER_CATALOG      | Tables, views and synonyms **CAT**                                                                   |
| USER_COL_COMMENTS | Comments on columns                                                                                  |
| USER_CONSTRAINTS  | Constraint definitions for tables                                                                    |
| USER_INDEXES      | All information about indexes created for tables **IND**                                             |
| USER_OBJECTS      | All database objects owned by the user **OBJ**                                                       |
| USER_TAB_COLUMNS  | Columns of the tables and views owned by the user **COLS**                                           |
| USER_TAB_COMMENTS | Comments on tables and views                                                                         |
| USER_TRIGGERS     | Triggers defined by the user                                                                         |
| USER_USERS        | Information about the current user                                                                   |
| USER_VIEWS        | Views defined by the user                                                                            |
| USER_SYS_PRIVS    | Shows which system privileges have been granted to the user                                          | 


## All
*Views include rows of the USER views and all information about objects that are accessible to the current user. The structure of these views is analogous to the structure of the USER views.*
| View         | Descripition                                                      |
| ------------ | ----------------------------------------------------------------- |
| ALL_CATALOG  | Owner, name and type of all accessible tables, views and synonyms |
| ALL_TABLES   | Owner and name of all accessible tables                           |
| ALL_OBJECTS  | Owner, type and name of accessible database objects               |
| ALL_TRIGGERS |                                                                   |
| ALL_USERS    |                                                                   |
| ALL_VIEWS             |                                                                   |

## DBA
*Encompass information about all database objects regardless of the owner. Only users with DBA privileges can access these views.*
| View           | Descipition                                         |
| -------------- | --------------------------------------------------- |
| DBA_TABLES     | Tables of all users in database                     |
| DBA_CATALOG    | Tables, views, and synonyms defined in the database |
| DBA_OBJECTS    | Object of all users                                 |
| DBA_DATA_FILES | Information about data files                        |
| DBA_USERS      | Information about all users known in the database                                                    |

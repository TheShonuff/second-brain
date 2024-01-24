---
tags:
  - SQL
---
# RENAME
- To change the name of a table
- The <code>RENAME</code> can also be used to rename columns using [[ALTER TABLE]] statement

## Syntax
```SQL
RENAME old_name TO new_name
```

### Example
```SQL
RENAME my_cd_collection TO my_music
```
>[!note] Rename table my_cd_collection to my_music

```SQL
ALTER TABLE persons
RENAME COLUMN first_name TO forename
```
>[!note] Rename the column first_name to forename in the persons table.


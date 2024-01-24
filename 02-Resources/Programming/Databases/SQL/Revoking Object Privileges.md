---
tags:
  - SQL
---
# Revoking Object Privileges
- You can remove privileges granted to other users by using the <code>REVOKE</code> statement
- The privileges specified are revoked from the users that you name and from any other users to whom those privileges were granted using [[WITH GRANT OPTION]] clause

## Syntax
```SQL
REVOKE {privilege [, privilege..]|ALL}
ON object
FROM {user[,user...]|role|PUBLIC} [CASCADE Constraints]}
```

>[!Warning] CASCADE CONSTRAINTS is required to remove any referential integrity constraints made to the object by means of the REFERENCES privilege.

### Example
```SQL
REVOKE SELECT, INSERT
ON clients
FROM scott_king;
```
>[!note] Revokes INSERT and SELECT privileges given to user scott_king

>[!warning] If the owner revokes a privilege from a user who granted privileges to other users, the revoke statement cascades to all privileges granted.


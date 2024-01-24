---
title: Enums Type
creation date: 2022-11-27 22:42
aliases: []
tags: reading ts filed
---

# Enums Type

Another type that exists only in TypeScript and not vanilla JavaScript is the enum type. This type is a enumerated list. Enum values are typically all uppercase. By default the list is enumerated starting at 0. If a number is assigned the rest of the list is enumerated after that assigned value.

If ADMIN is assigned the value 7 then READ_ONLY becomes 8 and AUTHOR becomes 9. We can also define numbers for each list item individually.
```js
enum Role {ADMIN = 7, READ_ONLY, AUTHOR}
```



# Footer
### Source
- 



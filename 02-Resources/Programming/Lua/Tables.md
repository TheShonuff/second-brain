---
title: Lua Tables
creation date: 2022-10-30 23:39
aliases: [lua tables] 
tags: lua filed
---

# Tables
Created: [[10-31-2022]]
- Tables are the main and *only* data structure in Lua.
- It's customary to start with a 1 **not** with a 0
- A Table is an *associative aray*
- Accepts numbers as indices as well as strings
- Does **not** accept *nil* as a value
- Tables are **objects**
Tables are created using constructor expressions
```lua
a = {} --creates a table
k = "x"
a[k] = 10 -- new entry, with key="x" and value="10"
a[20] = "great" --new entry, with key="20" and value="great"
```

### Title
- Programming in Lua
### Author
- Roberto Lerusalimschy
## References
1. chapter 5.1

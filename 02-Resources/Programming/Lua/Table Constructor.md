---
title: Lua Table Constructor
creation date: 2022-10-30 23:54
tags: lua/data-structure filed
aliases: [lua table constructor]
---

# Table Constructor
Created: [[10-31-2022]]
- Constructors are *expressions* that create and initialize tables.

The simplest constructor is:
```lua
a = {}
```

Initialize a table with data:
```lua
days = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturdau"}
```

Special syntax is initialize:
```lua
a = {a = 10, y = 10}
```
This is equivalent to
```lua
a = {}, a.x = 10; a.y = 20
```

We can mix record and list style
```lua
polyline = {color="blue",
			thickness=2,
			npoints=4,
			{x=0, y=0}
			{x=-10, y=0},
			{x=-10, y=1},
			{x=0, y=1}
			}
```

### Title
- Programming in Lua
### Author
- Roberto Lerusalimschy
## References
1. Chapter 5.2
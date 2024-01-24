---
title: Lua Table Library
creation date: 2022-11-04 01:06
tags: lua/data-structure filed
aliases: [lua table library]
---

# Table Library
Created: [[11-05-2022]]
Lua has a few bulitin functions to assist with working with [[Tables|tables]].
1. **table.insert** - inserts an element in a given position. 
```lua
t ={10,20,30}
table.insert(t,1,15)
t = {15,10,20,30}
```
2. **table.remove** - removes an element from a given position.
```lua
t = {10,20,30}
table.remove(t,1)
t = {20,30}
```
3. **table.move** - moves an element to a given position. 
```lua
table.move(a,f,e,t)
```
moves the elements in table a from index f until e to position t


# Footer
### Source
- Programming in lua
### Tags
- #literature #reading
#### Links
- 

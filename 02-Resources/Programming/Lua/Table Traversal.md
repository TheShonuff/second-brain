---
title: Lua Table Traversal
creation date: 2022-10-31 00:12
tags: lua/data-structure filed
aliases: [lua table traversal]
---

# Table Traversal
Created: [[11-01-2022]]
- We can traverse all key-value pairs with *pairs* iterator
```lua
t = {10, print, x=12, k="hi"}
for k, v in pairs(t) do
	print(k, v)
end
```
- For lists use the *ipairs* iterator
```lua
t = {10, print, 12, "hi"}
for k, v in ipairs(t) do 
	print(k,v)
end
```

### Title
- Programming Be Good
### Author
- Roberto Lerusalimschy
## References
1. 
#lua
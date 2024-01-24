---
title: multiple results
creation date: 2022-11-04 01:33
aliases: [lua functions multiple results]
tags: lua/functions filed
---

# Functions With Multiple Results
[[Lua Functions|Lua Functions]] can return multiple results by listing them after the **return** keyword.
```lua
function maximum (a)
	local mi = 1
	local m = a[mi]
	for 1 = 1, #a do
		if a[1] > m then 
			mi = i; m = a[i]
		end
	end
	return m, mi
end
```

Print(maximum({8,10,23,12,5})) would yield 23   3

> [!note]
> lua adjusts the number of results from a function to the circumstances of the call.

When called as a [[statement]], lua discards all results.
when called as an [[expression]], lua keeps only the first result.
We get all the results when the call is the last or only expression in a list of expressions.
```lua
function foo0 () end                 -- returns no results
function foo1 () return "a" end      -- returns 1 result
function foo2 () return "a", "b" end -- returns 2 results
```



# Footer
### Source
- Programming in Lua
### Tags
- #literature #reading #programming 
[[Lua MOC]]

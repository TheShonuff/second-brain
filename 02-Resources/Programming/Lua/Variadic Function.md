---
title: Lua Variadic Function
creation date: 2022-11-05 01:46
tags: lua/functions filed
aliases: [lua variadic function]
---

# Variadic Function
A function in lua can be [[variadic]] which can take a variable number of arguments. To start a variadic function we use **(...)**. Then function can access its extra agruments by using **(..)** again but now as an [[expression]] know as a [[varag expression]].
```lua
function nonils(...)
	local arg = table.pack(...)
	for i = 1, arg.n do
		if arg[i] == nil then return false end
	end
	return true
end

print(nonils(2,3,nil))     --> false
print(nonils(2,3))         --> true
print(nonils())            --> true
print(nonils(nil))         --> false   
```


# Footer
### Source
- Programming in Lua
### Tags
- #literature #reading


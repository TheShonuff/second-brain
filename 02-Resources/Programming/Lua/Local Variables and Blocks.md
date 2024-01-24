---
title: Local Variables and Blocks
creation date: 2022-11-05 13:51
aliases: [lua variables]
tags: lua/basics filed
---

# Local Variables and Blocks
By default all variables are global unless specified by the **local** tag which it's scope is limited to the [[block]] where it's declared. 

Lua is a dynamically typed language. Meaning there are no type definitions. Much like javascript. Lua Variables can contain types: strings, numbers etc...

There are 7 Basic Value Types:
 1. nil
 2. numbers
 3. string
 4. function
 5. CFunction
 6. userdata
 7. table

incrementing variables in done by assigning the variable to be incremented or decremented the value plus or minus the value
```lua
score = 0
score = score + 1
```

Example of scoping in Lua. 
```lua
x = 10
local i = 1             --local to the chunk

while i <= x do
	local x - i * 2     --local to the while loop
	print(X)
	i = i + 1
end

if i > 20 then
	local x              --local to the then body
	x = 20
	print(x + 2)
else
	print(x)             -- prints global x = 10
end
```

> [!note]
> It's good programming practice to use local whenever possible

# Footer
### Source
- Programming in Lua
### Tags
- #literature #reading
[[Lua MOC]]

---
tags:
  - lua
---


# Lua Functions
lua functions are the main mechanism for abstraction of statements and expressions. They are similar to languages we already know like [javascript]. What's special about lua functions is they can return [[Functions With Multiple Results|mutiple results]].

```lua
function add(a)
	local sum = 0
	for i = 1, #a do 
		sum = sum + a[1]
	end
	return sum
end
```


# Footer
### Source
- 
### Tags
- #literature #reading
#### Links
- [[Lua MOC]]

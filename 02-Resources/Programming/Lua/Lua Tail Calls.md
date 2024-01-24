---
title: Lua Tail Calls
creation date: 2022-11-05 01:57
tags:
  - lua
---

# Lua Tail Calls
A tail call occurs when the function returns a function.
```lua
function f(x) x = x + 1; return g(X) end
```

- See also [[Tail Call Elimination]]

# Footer
### Source
- Programming in Lua
### Tags
- #literature #reading


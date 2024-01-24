---
title: Functions
creation date: 2022-11-12 14:16
tags: shell/scripting filed
---

# Functions

Functions are typically declared at the top of the script.

Decalring a function with **function** is *optinal*

A function may return a value in one of four ways:
1. Change the state of a variable or variables.
2. Use the exit command to end the shell script
3. use the return command to end the function and return the value to the caller
4. Echo output to [[stdout]] which will be caught by the caller.

> [!note] The shell uses **Dynamic Scoping**

With dynamic scoping, visible variables and their values are a result of the sequence of calls.

For example, if a variable *var* is declared as local in function **func1** and **func1** calls another function **func2**, references to *var* made from within **func2** will resolve to the local variable *var* from **func1**, shadowing any global variable named *var*.



# Footer
### Source
- 
### Tags
- #reading


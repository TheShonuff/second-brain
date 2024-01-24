---
tags:
  - python
---

---
Created: [[06-30-2023]]
tags: python
---
# Python Namespaces
- Maps names to objects.
- The Python interpreter uses namespaces to track all of the objects in a program.
- A **namespace** is a normal Python [[Dictionaries|dictionary]] whose keys are the names and whose values are the objects. 
	- `locals()` accesses local built-in functions
	- `globals()` accesses global built-in functions

- **Scope** is the area of code where a name is visible.
- Namespaces are used to make scope work.
- Each **scope** has it's own namespace.
	
- Built-in Scope = Contains all of the built-in names of Python
- Global Scope = Contains all globally defined names outside of any functions.
- Local Scope = Refers to scope within the currently executing function but is the same as global scope if no function is executing.



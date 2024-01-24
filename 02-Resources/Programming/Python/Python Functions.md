---
tags:
  - python
---

---
# Python Functions
- **Modular development** is the process of dividing a program into separate modules that can be developed and tested separately and integrated into a single program.
	- Avoids writing redundant code

>[!tip] Functions in Python are written using snake_case


### Function Stubs
- Function definitions whose statements haven't been written yet. 
	- **pass** performs no operation except to act as a placeholder for a required statement.
	- Using `print()` is another common operation to act as a placeholder.
	- `raise NotImplementedError` indicates that the function is not implemented and causes the program to stop execution.
	- 

## Void
A function with no return statement.

- `randint()` a method in `random` library that chooses a random number between an upper and lower bound.
```Python
import random

print(random.randint(0,9))
```

## Parameter
- Is the name defined in the parathesis of the function and can be used in the function body.
## Arguments
- Passed to functions by reference
- **pass-by-assignment**
- When a function is called, new local variables are created in the functions local namespace by binding the names in the parameter list to the passed arguments.
- There types of arguments
	- *Positional Arguments*
	- *Keyword Arguments*
	- *Default Arguments*

### Keyword Arguments
- Allow arguments to map to parameters by name instead of implicitly by position in the argument list.
- **The argument list does not need to follow a specific order.**
>[!warning] Must come after positional arguments

### Default Arugments
- function can optionally omit an argument and the default parameter values will be substitued instead for the omitted argument.
- Any argument can be omitted as long as  that argument has a default value.

## Arbitrary Argument Lists
- `*args` parameter collects optional positional parameters into an **arbitray argument list**.
- `**kwargs` **Keyword arguments** creates a dictionary containing extra agruments not defined in the function definition. 

## Functions are Objects
- Functions have a type, identity and a value.
- Function definitions creates a new object function.
- A part of the value of a function is compiled **bytecode** that represents the statements to be executed by the function.
- A **Bytecode** is a low-level operation, such as adding, subtracting, or loading from memory. One Python statement may require multiple bytecode operations.
---
title: PHP Functions
Created: 2024-01-02 20:55
tags:
  - php
aliases:
---
# PHP Functions
- The `function` keyword is used to start a function.
- The function is surround in curly brackets `{}`
>[!tip] snake_case is used for variable names
- Functions are invoked like any other language
- Functions can return a value using the `return` keyword
	- The `return` keyword immediately terminates a function

>[!tip] Functions without a `return` keyword return a special value -> `NULL`

## Parameters
- parameters can be defined in the function definition.
	- The actual value passed in the function is known as the `argument`

## Pass By Reference
- If we want to make permanent changes to variable within a function
	- Prepend the parameter name with `&`
	- Assigns the parameter to be an alias for the argument variable.
		- Both will refer to the same spot in the memory.

```Php
function addXPermanently (&$param)
{
  $param = $param . "X";
  echo $param;
};
$word = "Hello";
addXPermanently($word); // Prints: HelloX
echo $word; // Prints: HelloX
```


## Variable Scope
- to use variables outside the function use `global` keyword.




---
title: Arrays
Created: 2024-01-11 20:50
tags:
  - php
aliases:
---
# PHP Arrays
- Ordered array's can be constructed using `array()`
	- Also can be created using square brackets `[ ]`
- Can store *any* data type as well as mixed data types.
- Uses zero indexing


- `count()` is used to get the number of elements in an array.

- `print_r()` is used to display the contents of an array with index's.
- `implode()` will print the contents only.
	- Takes two arguments.
## Accessing elements
- individual elements can be accessed using typical syntax. `array[index]`
## Appending and changing elements
- Adding to the end of the array is simpley `array[] = appended_item`
- To change an element access the elements index and set the new value.
### Pop
- `array_pop()` takes an array as an argument and removes the last element.
### Push
- `array_push()` takes an array as its first argument and then the elements to be added to the end of the array.
### shift
- `array_shift()` removes the first element of an array and returns the value. Each of the elements of the array will then be shifted down 1 index.
### unshift
- `array_unshift()` takes an array as its first argument and then the values to be added to the beginning of the array.
## Nested Arrays
- Like any other language to access the elements stack the brackets. `array[0][0]`
- using `print_r()` is an easy way to visiualize the nested array.
## Joining Arrays
- Arrays can be combined using the `+` operator.
## Assign by Value or by Reference 
- There are two ways to assign one variable to another:
	- **by value** - this creates two variables that hold copies of the same value but remain independent entities
	- **by reference** - this creates two variables names (aliases) which point to the same space in memory. They cannot be modified separately.

>[!warning] When passing arrays into functios, we'll need to be conscious of whether the arrays are being passed by value or by reference.



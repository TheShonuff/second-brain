---
title: Recursion in Python
Created: 2023-10-03 21:00
tags:
  - algorithms
aliases:
---

# Recursion in Python
- When you call a [[Python Functions|function]] in python, the interpreter creates a new local namespace.
- Once function can call another, even if they both define objects with the same name, they all exist in their own namespaces.

- [[Recursion]] is simply a function that calls it self with two features.
	- **Base Case**: a condition that evaluates the current input to stop the recursion
	- **Recursive Step**: one or more calls to the recursive function to bring the input closer to the base case.
- **Execution Context** contains the variables within each recursive function call
```Python
def countdown(n):
	print(n)
	if n == 0:
		return
	else:
		countdown(n-1)
```
>[!note] The base case occurs when **n** is zero. In the recursion call, the argument is one less than the current value of n. Moving n closer to to the base case.

## Recursive Data Structures
- Trees are a recursive data structure because their definition is self-referential.
- [[Binary Search Tree]]
	- Reference two children **at most** per tree node
	- The *left* child of the tree must contain a value *lesser than* its parent
	- The *right* child of the tree must contain a value *greater than* its parent
## When to use Recursion
### Nested Lists
- A nested list can be traversed and flattened using a recursive function.
- The **base case** evaluates an element in the list. If it's not another list, the single element is append to the flat list.
```Python
def flatten(mylist)
	flatlist = []
	for element in mylist:
	if type(element) == list:
		flatlist += flatten(element)
	else:
		flatlist += element
	return flatlist
```

### Sum Digits With Recursion
- Summing the digits of a number $552 = 5 + 5 + 2 = 12$
```Python
def sum_digits(n):
	if n <= 9:
		return n
	last_digit = n % 10
	return sum_digits(n // 10) + last_digit
```

### Palindrome
- A word that can be read the same both ways
```Python
def is_palindrome(str):
	if len(str) < 2:
		return True
	if str[0] != str[-1]:
		return False
	return is_palindrom(str[1:-1])
```

### Find Minimum in List
```Python
def find_min(my_list):
	if len(my_list) == 0:
		return None
	if len(my_list) == 1:
		return my_list[0]

	temp = my_list[0] if my_list[0] < my_list[1] else my_list[1]
	my_list[1] = temp
	return find_min(my_list[1:])
	
```
### Fibonacci Recursion
- Computing the number of a Fibonacci number can be computedusing recursion.
- Given an input of index N, the recursive function has two base cases.
	- The the index is zero or 1
- The recursive function returns the sum of the index minus 1 and the index minus 2.
```Python
def fibonacci(n):
	if n == 1:
		return 1
	if n == 0:
		return 0
	return fibonacci(n-2) + fibonacci(n-1)
```

### Factorial
```Python
def factorial(n):
	return 1 if n <= 1 else n * factorial(n-1)

'''
The for loop example
'''

def factorial(n):
	return_value = 1
	for in range(2, n+1):
		return_value *= i
	return return_value
```

### Binary Search Tree
- A [[Binary Search]] tree algorithm with recursion.
```Python
def build_bst(my_list):
	if len(my_list) == 0:
		return "No Child"
	middle_index = len(my_list) // 2
	middle_value = my_list[middle_index]

	tree_node = {"data": middle_value}
	tree_node = ["lefT_child"] = build_bst(my_list[:middle_index])
	tree_node = ["right_child"] = build_bst(my_list[middle_index +1 :])

	return tree_node
```






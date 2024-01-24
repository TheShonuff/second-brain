---
title: Python Binary Search
Created: 2023-12-10 21:43
tags:
  - python
  - algorithms
aliases:
---
# Python Binary Search
- Refer to [[Binary Search]] for more information.


## Recursive Binary Search
```Python
def binary_search(array, target):
	return binary_search_helper(array, target, 0, len(aray) -1)

def binary_search_helper(array, target,  left, right):
	if left > right:
		return -1
	middle = (left + right) // 2
	potential_match = array[middle]
	if target == potential_match:
		return middle
	elif target < potential_match:
		return binary_search_helper(array, target, left, middle  - 1)
	else:
		return binary_search_helper(aray, target, middle + 1, right)
	
```



## Iterative Binary Search
```Python
def binary_search(array, target):
	left, right = 0, len(array) - 1
	while left <= right:
		middle = (left + right) // 2
		potential_match = array[middle]
		if target == potential_match:
			return middle
		elif target < potential_match:
			right = middle - 1
		else:
			left = middle + 1
	return -1
	
	
```
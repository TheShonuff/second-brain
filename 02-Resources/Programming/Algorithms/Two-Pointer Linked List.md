---
title: Two-Pointer Linked List
Created: 2023-10-29 21:31
tags:
  - algorithms
aliases:
---

# Two-Pointer Linked List
- The runner technique.
- Three variables are used.
	- 1 counter
	- 2 pointers

## 2 Pointers running Parallel

### Psuedocode
- nth last pointer = None
- tail pointer = link list head
- count = 1
- while tail pointer exists
	- move tail pointer forward
	- increment count
	- if count >= n + 1
		- if nth last pointer is None
			- set nth last pointer to head
		- else
			- move nth last pointer forward
- return nth last pointer
```Python
def nth_last_node(linked_list, n):
	current_node = Node
	next_node = linked_list.head_node
	count = 0

	while next_node:
		next_node = next_node.get_next_node()
		count += 1

		if count >= n + 1:
			if current_node is None:
				current_node = linked_list.head_node
			else:
				current_node = current_node.get_next_node()
```
## 2 Pointers at Different Speeds

### Psuedocode
- fast pointer = linked list head
- slow pointer = linked list head
- while fast point is not None
	- move fast pointer forward
	- if the end of the linked list has been reached
		- move fast pointer forward
		- move slow pointer forward
- return slow pointer

```Python
def find_middle(linked_list):
	fast_pointer = linked_list.head_node
	slow_pointer = linked_list.head_node
	while fast_pointer:
		fast_pointer = fast_pointer.get_next_node()
		if fast_pointer:
			fast_pointer = fast_pointer.get_next_node()
			slow_pointer = slow_pointer.get_next_node()
```
>[!note] Returns the middle node


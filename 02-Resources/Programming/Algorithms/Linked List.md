---
title: Linked List
Created: 2023-10-13 22:29
tags:
  - algorithms
aliases:
---
# Linked List
- Ordered collection of objects.
- Each element of a linked list is called a [[Nodes|node]].
- Every **node** has two different fields:
	- **Data** contains the value to be stored in the node.
	- **Next** contains a reference to the next node on the list.
- The first **node** is called the **head**.
- The last node must have its next reference point to **None**.

![[Pasted image 20231027214048 1.png]]
## Practical Applications
- [[Stacks]] and queues. 

## Performance
- Memory usage of [[Lists]] and **linked lists** are very similar in Python.

### Insertion and Deletion of Elements
- Much more straight forward than [[Lists]].
- Time complexity is $O(1)$

### Retrieval of Elements
- Linked lists suffer due to having to traverse the entire list
- Time complexity is $O(n)$

## Creating a Linked List
- First get the **head** node.
```Python
class Node:
	def __init__(self, value, next_node=None):
		self.value = value
		self.next_node = next_node
		
	def get_value(self):
		return self.value
		
	def get_next_node(self):
		return self.next_node
		
	def set_next_node(self, next_node)
		self.next_node = next_node
		
	def __repr__(self):
		return self.data

```

### Insert at beginning
```Python
	def insert_beginning(self, new_value):
		new_node = Node(new_value)
		new_node.set_next_node(self.head_node)
		self.head_node = new_node
```

### Full Class
```Python
class LinkedList:
	def __init__(self, value=None):
		self.head_node = Node(value)
		
	def get_head_node(self):
		return self.head_node
		
	def insert_beginning(self, new_value):
		new_node = Node(new_value)
		new_node.set_next_node(self.head_node)
		self.head_node = new_node
		
	def remove_node(self, value_to_remove):
		current_node = self.get_head_node()
		
		if current_node.get_value() == value_to_remove()
			self.head_node = current_node.get_next_node()
		else:
			while current_node:
				next_node = current_node.get_next_node()
				
				if next_node.get_value() == value_to_remove:
					current_node.set_next_node(next_node.get_next_node())
					current_node = None
				else:
					current_node = next_node
```


### Traversing a Linked List
- The most common operation with linked lists is iterating.
- Always validate that the current node *is not none*
```Python
	def stringify_list(self):
		string = ''
		current_node = self.get_head_node()
		while current_node:
			string += str(current_node.get_value()) + '\n'
			current_node = current_node.next_node
		return string
```


```Python
def __iter__(self):
	node = self.head
	while node is not None:
		yield node
		node = node.next
```
>[!note] Another method of iteration

## Swapping Elements
- need to keep track of two nodes.
- Given a linked list and the elements to be swapped **val1** and **val2** 4 values need to be tracked
	- **node1** - the node that matches *val1*
	- **node1_prev:** - *node1*'s previous node
	- **node2** - the node that matches *val2*
	- **node2_prev** - *node2*'s previous node

### Psuedocode
- Iterate through the list lookg for the node that matches **val1** to be swapped(**node1**), keeping track of the node's previous node as you iterate(**node1_prev**)
- Repeat step 1 looking for the node that matches **val2**
- IF **node1_prev** is None, **node1** was the head of the list, set the lists head to **node2**
- otherwise, set **node1_prev**'s next node to **node2**
- if **node2_prev** is None, set the list's head to **node1**
- otherwise, set **node2_prev**'s next node to **node1**
- set **node1**'s next node to **node2**'s next node
- set **node2**'s next node to **node1**'s next node

### Finding the matching and preceding nodes

```Python
def swap_node(input_list, val1, val2):
	node1 = input_list.head_node
	node2 = input_list.head_node
	node1_prev = None
	node2_prev = None

	while node1 is not None:
		if node1.get_value() == val1:
			break
		node1_prev = node1
		node1 = node1.get_next_node()
	while node2 is not Nonde:
		if node2.get_value() == val2:
			break
		node2_preve = node2
		node2 = node2.get_next_node()
```

### Updating the Preceding Nodes' Pointers
```Python
	if node1_prev is None:
		input_list.head_node = node2
	else:
		input_list.set_next_node(node2)

	if node2_prev is None:
		input_list.head_node = node1
	else:
		input_list.set_next_node(node1)

	temp = node1.get_next_node()
	nod21.set_next_node(node2.get_next_node())
	node2.set_next_node(temp)
```
## Leet Code Problem
Given the `head` of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list **sorted** as well.
**Input** `head = [1,1,2]`
**Output** `[1,2]`

**Input** `head = [1,1,2,3,3]`
**Output** `[1,2,3]`

```Python
```python
class Solution(object):
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

    def deleteDuplicates(self, head):
        current = head
        while current is not None and current.next is not None:
            if current.next.val == current.val:
                current.next = current.next.next
            else:
                current = current.next
        return head
```

```Python
# Definition for singly-linked list.
# class ListNode:
# def __init__(self, val=0, next=None):
# self.val = val
# self.next = next
class Solution:
def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
	current = head
	while current is not None and current.next is not None:
		if current.next.val == current.val:
			current.next = current.next.next
		else:
			current = current.next

	return head
```
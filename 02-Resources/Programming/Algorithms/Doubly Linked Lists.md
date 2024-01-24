---
title: Doubly Linked Lists
Created: 2023-10-31 20:32
tags:
  - algorithms
aliases:
---

---
# Doubly Linked Lists
- Like a single [[Linked List]], a **doubly linked list** is comprised of a series of nodes.
- There's a **head** node. Previous pointer is set to *None*
- There's a **tail** node. Next pointer is set to *None*

>[!tip] Each node will have a previous and next pointer

>[!tip] Think of a daily commute on a subway train. Your home is the **head** and the destination is the **tail**. Every stop inbetween is a [[Nodes|node]].

## Adding to a list
- Need to set node's previous pointer.
- Need to update the tail of list if necessary.

### Adding to the head
- Check if there is currently a head node.
	- If there isn't a head node. Simply add to list
	- If there list isn't empty
		- Set the *current* head's previous pointer to our new head
		- Set the *new* heads's next pointer to the current head
		- set the *new* head's previous pointer to *None*
### Adding to the tail
- if the list is empty, make the new node the head and tail of the list and set pointers to *None*
- if there list isn't empty
	- Set the *current* head's previous pointer to our new head
	- Set the *new* head's next pointer to the current head
	- Set the *new* head's previous pointer to *None*

## Removing from the list
- The extra pointer and tail proerty makes the removal more complicated.

### Removing the head
- Set the previous pointer of the new head to *None*
- Update the head property of the list.

### Removing the tail
- Update the pointer at the end of the list.
- Set the next pointer of the new tail to *None*
- Update the tail property of the list.

### Removing from the middle
- There are two pointers that must be updated.
- Set the removed node's preceding node's next pointer to it's following node
- Set the mremoved node's following node's previous pointer to it's preceding node.


## Node Class and Constructor
```Python
class Node:
	def __init__(self, value, next_node=None, prev_node=None):
		self.value = value
		self.next_node = next_node
		self.prev_node = prev_node
		
	def set_next_node(self, next_node):
		self.next_node = next_node
		
	def get_next_node(self):
		return self.next_node
		
	def set_prev_node(self, prev_node):
		self.prev_node = prev_node
		
	def get_prev_node(self):
		return self.prev_node
		
	def get_value(self)
		return self.value
```

```Python
class DoublyLinkedList:
	def __init__(self):
		self.head_node = None
		self.tail_node = None
	def add_to_head(self, new_value):
		new_head = Node(new_value)
		current_head = self.head_node
		
		if current_head is not None:
			current_head.set_prev_node(new_head)
			new_head.set_next_node(current_head)
			
		self.head_node = new_head

		if self.tail_node is None
			self.tail_node = new_head

	def add_to_tail(self, new_value):
		new_tail = Node(new_value):
		current_tail = self.tail_node

		if current_tail is not None:
			current_tail.set_next_node(new_tail):
			new_tail.set_prev_node(current_tail)

		self.tail_node = new_tail

		if self.head_node is None:
			self.head_node = new_tail

	def remove_head(self):
		removed_head = self.head_node
		if removed_head is None:
			return None
			
		self.head_node = removed_heads.get_next_node()
		
		if self.head_node is not None:
			self.head_node.set_prev_node(None)
			
		if remove_head == self.tail_node
			self.remove_tail()
			
		return removed_head.get_value()
		
	def remove_tail(self):
		removed_tail = self.tail_node
		if removed_tail is None:
			return None

		self.tail_node = removed_tail.get_prev_node()

		if self.tail_node is not None:
			self.tail_node.set_next_node(None)
			
		if removed_tail == self.head_node
			self.remove_head()

		return removed_tail.get_value()

	def remove_by_value(self, value_to_remove):
		node_to_remove = None
		current_head = self.head_node
		
		while current_head is not None:
			if current_node.get_value() == value_to_remove:
				node_to_remove = current_node
				break
			current_node = current_node.get_next_node()

		if node_to_remove is None:
			return None
		if node_to_remove == self.head_node:
			self.remove_head()
		elif node_to_remove == self.tail_node:
			self.remove_tail()
		else:
			next_node = node_to_remove.get_next_node()
			prev_node = node_to_remove.get_prev_node()
			next_node.set_prev_node(prev_node)
			prev_node.set_next_node(next_node)
		return node_to_remove

	def stringify_list(self):
		string_list = ""
		current_node = self.head_node
		while current_node:
			if curren_node.get_value() is not None:
				string_list += str(current_node.get_value() + "\n")
			current_node = current_node.get_next_node()
		return string_list
		
			
```
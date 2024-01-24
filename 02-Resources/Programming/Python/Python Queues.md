---
title: Python Queues
Created: 2023-11-03 21:33
tags:
  - python
aliases:
---

---
# Python Queues
- A *data structure* contains an ordered set of data

>[!tip] Follows FIFO (first in, first out)

- Three methods for interaction:
	- **Enqueue** - Adds data to the *back* or *end* of the queue
	- **Dequeue** - Proves and removes data from the *front* or *beginning*
	- **Peek** - reveals data from the *front* without removing

- A *Queue underflow* occurs when you try to **dequeue** from an empty queue
## Implementation
- Can be implemented using a [[Linked List]] as the underlying data structure.
- The front of the queue is the **head**
- The back of the queue is the **tail**
- Any traversal or modifications to other nodes is disallowed. 
- If there's a limit to the size of a queue it's a **bounded queue**



```Python
from node import Node

class Queue:
	def __init__(self,max_size=None):
		self.head = None
		self.tail = None
		self.size = 0
		self.max_size = max_size
	def peek(self):
		if self.is_empty():
			print("Nothing to see here!")
		else:
			return self.head.get_value()
	def get_size(self):
		return self.size
	def has_space(self):
		if self.max_size is None:
			return True
		else:
			return self.max_size > self.get_size()
	def is_empty(self):
		if self.size == 0:
			return True
		else:
			return False
```

## Enqueue
```Python
	def enqueue(self,value):
		if self.has_space():
			item_to_add = Node(value)
			print(f'Adding {item_to_add.get_value()} to the queue!')
			if self.is_empty():
				self.head = item_to_add
				self.tail = item_to_add
			else:
				self.tail.set_next_node(item_to_add)
				self.tail = item_to_add
			self.size += 1
		else:
			print("Sorry, no more room!")
```

## Dequeue
```Python
	def dequeue(self):
		if self.get_size() > 0:
			item_to_remove = self.head
			print("Removing " + str(item_to_remove.get_value()) " from the queue!")
			if self.get_size() == 1:
				self.head = None
				self.tail = None
			else:
				self.head = self.head.get_next_node()
		else:
			print("This queue is totally empty")
		self.size -= 1
		return self.head.get_value()

```
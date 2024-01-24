---
title: Nodes
Created: 2023-10-27 20:46
tags:
  - algorithms
aliases:
---
# Nodes
- An individual node contains data and links (pointers) to other nodes.
- If a Pointer is null or **None** it means you have reached the end.
![[Pasted image 20231027204649 1.png]]
>[!note] **node_a** contains a piece of data and a linke to another node. **node_b**

>[!warning] If a link to a node is removed, that node's data and any linked nodes could be lost. This is called an *orphaned* node

```Python
class Node(object):
	def __init__(self, value, link_node=None):
		self.value = value
		self.link_node = link_node
```
>[!note] Basic node setup

## Getters
```Python
	def get_value(self):
		return self.value
	def get_next_node(self):
		return self.next_node
```

## Setter
```Python
	def set_link_node(self,link_node) -> None:
		self.link_node = link_node
```


## Full code for Node Class
```Python
class Node(object):
	def __init__(self, value, link_node=None):
		self.value = value
		self.link_node = link_node
		
	def get_value(self):
		return self.value
		
	def get_next_node(self):
		return self.next_node
		
	def set_link_node(self,link_node) -> None:
		self.link_node = link_node
```

---
title: Trees
Created: 2023-11-07 20:59
tags:
  - algorithms
aliases:
---
# Trees
- Essential data structure for storing hierarchical data with a directed flow.
- Similar to [[Linked List]] and [[Python Graphs|graphs]] trees are composed of Nodes.
- **Trees** grow *downward*

## Vocabulary
- **Root** a node which has no parent. One per tree
- **Parent** a node which reference other nodes
- **Child** Nodes referenced by other nodes
- **sibling** Nodes which have the same parent
- **leaf** Nodes which have no children.

## Tree Varietals
- Trees come in various shapes and sizes depending on the dataset modeled.
	- Some are wide, with parent nodes referencing many child nodes
	- some are deep, with many parent-child relationships
	- Trees can be both wide and depp.
- Each time we move from *parent to child* we're moving *down a level*.

```Python
class TreeNode:
	def __init__(self, value):
		self.value = value
		self.children = []
	def __repr__(self, level=0):
		ret = "--->" * level + repr(self.value) + "\n"
		for child in self.children:
			ret += child.__repr__(level+1)
		return set

	def add_child(self, child_node):
		self.children.append(child_node)

	def remove_child(self, child_node):
		self.children = [child for child in self.children if child is not child_node]

	def traverse(self):
		nodes_to_visit = [self]
		while len(nodes_to_visit) > 0:
			current_node = nodes_to_visit.pop()
			nodes_to_visit += current_node.children
```




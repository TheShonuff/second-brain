---
title: Binary Search Tree
Created: 2023-10-26 18:51
tags:
  - algorithms
  - python
aliases:
---

# Binary Search Tree
- A tree where each node is a value greater than all of its left child nodes and less than all of its right child nodes.
- [Medium](https://medium.com/odscjournal/binary-search-tree-implementation-in-python-5f8a50341eaf)

## Terminology
- [[Nodes|Node]]: is the fundamental part of a tree.
- **Edge**: Connectes two nodes to show that there is a relationship
	- Every node (Except the root) is connected by exactly one incoming *edge* from another node
- **Root**: The top of the binary search tree. 
	- There are no incoming edges
- **Path**: An ordered list of nodes that are connected by edges.
- **Children**: descendants of a *parent* node
- **Parent**: Connects to several *children* nodes
- **Leaf Node**: has no *children*
- **Level**: The number of *edges* on the path from the root node to n.
- **Height**: Equal to the maximum level of any node in the tree.
- **Balanced Tree**: Equal levels for both left and right subtrees.
- **Complete Binary Tree**: Every level is full except the last level and it will only be missing nodes on the right.

## Tree Traversal
- There are three systematic ways to visit all the nodes of a tree:
	- preorder - root > left > right -> [[InFix, PreFix and PostFix Expressions#Prefix|PreFix]]
	- inorder - left > root > right -> [[InFix, PreFix and PostFix Expressions#Infix|InFix]]
	- postorder - left > right > root -> [[InFix, PreFix and PostFix Expressions#Postfix - Reverse Polish Notation|PostFix]]


## Implementation

```Python
class BSTNode:
	def __init__(self, val=None):
		self.left = None
		self.right = None
		self.val = val
```



### Insert
```Python
	def Add_Node(self,val):
		if val == self.val:
			return

		if val < self.val:
			if self.left:
				self.left.Add_Node(val)
			else:
				self.left = BSTNode(val)

		else:
			if self.right:
				self.right.Add_Node(val)
			else:
				self.right = BSTNode(val)
```


### Find Node
```Python
	def Find_Node(self,val)
		if self.val == val:
			return True
		if val < self.val:
			if self.left:
				return self.left.Find_Node(val)
			else:
				return False
		if val > self.val
			if self.right:
				return self.right.Find_Node(val)
```
### Get Min Max
```Python
	def get_min(self):
		current = self
		while current.left is not None:
			current = current.left
		return current.val
	def get_max(self)
		current = self
		while current.right is not None:
			current = current.right
		return current.val
```


### Delete
```Python
	def delete(self, val):
		if self == None:
			return self
		if val < self.val
			self.left = self.left.delete(val)
			return self
		if val > self.val:
			self.right = self.right.delte(val)
			return self
		if self.right == None
			return self.left
		if self.left == None
			return self.right
		min_larger_node = self.right
		while min_larger_node.left:
			min_larger_node = min_larger_node.left
		self.val = min_larger_node.val
		self.right = self.right.delete(min_larger_node.val)
		return self
```
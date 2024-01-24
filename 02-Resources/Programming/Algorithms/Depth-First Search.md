---
title: Depth-First Search
Created: 2023-11-08 22:59
tags:
  - algorithms
aliases:
---
# Depth-First Search
- space & time complexity of $O(n)$
- Algorithm beings at the root node and explores deeper untils it reaches a leaf node.
- Uses a [[Python Stacks|stack]] to store roots of unexplored subtrees.
>[!tip] Checks the values along a path of vertices before moving to another path

![DFS Video](https://www.youtube.com/watch?v=0_ZzqX5bpyA)

## Recursive Implementation
- If the input node value matches our target value then reutrn the input node.
- For each child of the input node, recursively call this function and return the first non-null value returned by a recursive call
- If this root node has no children, or the recursive calls did not reutrn any node, then return null.
```Python
def dfs(root, target):
	if root.value == target:
		return root
	for child in root.children:
		node_found = dfs(child, target)
		if node_found is not None:
			return node_found
	return None
```

### Print The Path
```Python
def dfs(root, target, path=())
	path = path + (root,)
	if root.value == target:
		return path
	for child in root.children:
		node_found = dfs(child, target, path)
		if path_found is not None:
			return path_found
	return None
```
## Iterative Implementation
- Need to manually implement a stack




---
title: Breadth-First Search
Created: 2023-11-08 20:55
tags:
  - algorithms
aliases:
---

# Breadth-First Search
- Tree traversal algorithm that searches a tree level by level.
- Starts at the root node and works its way through every sibling node on a level.
- There are many ways to implement a *breadth-first search*
- The steps for implementation
	- Import values into a tree data structure
	- Determine the root node of the tree and the goal value to search for
	- Create a queue of node paths that lead to the nodes that need to be searched
	- Get a path from the gueue to obtain the next node to search
	- If the goal value isn't found in the node, add a path to the queue for each of the node's children.

>[!tip] Checks the values of all the neighboring vertices before moving into a never level.

![BFS Search Video](https://youtu.be/WiasVg9M81I)
### Level-By-Level Search
- Iteratively checks child nodes in the order they are placed in a queue.
![breadth-first flow chart](https://static-assets.codecademy.com/Courses/CS102-Data-Structures-And-Algorithms/Breadth-First-Search-And-Depth-First-Search/BFSDiagram-1.svg)

## Implmentation
### TreeNode
```Python
from collections import deque

class TreeNode:
	def __init__(self,value):
		self.value = value
		self.children = []
	def __str__(self):
		stack = deque()
		stack.append([self,0])
		level_str = "\n"
		while len(stack) > 0:
			node, level = stack.pop()

			if level > 0:
				level_str += "| "*(level-1)+ "|-"
			level_str += str(node.value)
			level_str += "\n"
			level += 1
			for child in reversed(node.children)
				stack.append([child,level])

		return level_str
```

### Breadth-first Search function
```Python
from collections import deque

def bfs(root_node, goal_value):
	path_queue = deque()
	initial_path = [root_node]
	path_queue.appendleft(initial_path)

	while path_queue:
		current_path = path_queue.pop()
		current_node = current_path[-1]
		if current_node.value == goal_value
			return current_path
		for child in current_node.children:
			new_path = current_path[:]
			new_path.append(child)
			path_queue.appendleft(new_path)
		
	return None
```
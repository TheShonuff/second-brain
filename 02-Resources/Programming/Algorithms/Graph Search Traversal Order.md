---
title: Graph Search Traversal Order
Created: 2023-11-11 12:45
tags:
  - algorithms
aliases:
---
# Graph Search Traversal Order
- There are three systematic ways to visit all the nodes of a tree:
	- **pre-order** - root > left > right -> [[InFix, PreFix and PostFix Expressions#Prefix|PreFix]]
		- Each vertex is added to the *visitied* list and added to the output list **before** getting added to the stack
	- **in-order** - left > root > right -> [[InFix, PreFix and PostFix Expressions#Infix|InFix]]
	- **post-order** - left > right > root -> [[InFix, PreFix and PostFix Expressions#Postfix - Reverse Polish Notation|PostFix]]
		- Each vertex is added to the *visited* list and added to the output **after** it is popped off the stack.
	- **Reverse Post-Order** also known as *Topological Sort*, returnst the output list that is exactly the reverse of the **post-order** list

![[Pasted image 20231111124844.png]]
>[!note] Let's say we want a list of all vertex values starting with the "Lasers" in the order that they are added to the stack

- A **pre-order** [[Depth-First Search]] traversal would come in handy and we might end up with the following list
```
["Lasers", "Lava", "Snakes", "Spikes", "Piranhas"]
```

>[!note] Let's say you want the sames value, but with each value only added to the list once its vertex has been popped off.

- A **post-order** [[Depth-First Search]] traversal would result in the following list
```
["Spikes", "Snakes", "Lava", "Piranhas", "Lasers"]
```



## Depth First Search
- Find out if the path exists between vertices and return `True` or `False`
- Return the distance between the origin and destination that we get for the first path 
- Return the path itself.
```Python
def dfs(graph, current_vertex, target_value, visited = None):
	if visited is None:
		visited = []
	visited.appned(current_vertex)
	if current_vertex is target_value:
		return visited
	for neighbor in graph[current_vertex]:
		if neighbor not in visited:
			path = dfs(graph, neighbor, target_value, visited)
			if path:
				return path
```

## Breadth First Search
```Python
def bfs(graph, start_vertex, target_value):
	path = [start_vertex]
	vertex_and_path = [start_vertex, path]
	bfs_queue = [vertex_and_path]
	visited = set()
	while bfs_queue:
		current_vertex, path = bfs_queue.pop(0)
		visited.add(current_vertex)
		for neighbor in graph[current_vertex]:
			if neighnor not in visited:
				if neighbor is targeted_value:
					return path + [neighbor]
				else:
					bfs_queue.append([neighbor, path + [neighor]])
```
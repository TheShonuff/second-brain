---
title: Shortest Path Algorithm
Created: 2023-11-15 22:03
tags:
  - algorithm
aliases:
---

# Shortest Path Algorithm
- Algorithm uses [[Breadth-First Search]]

## PsuedoCode
- Build the graph from the array of edges, initialize all nodes distance to src to 0
- Start from the source node and put it into a queue, with its distance to source set to 0.
- while queue is not empy
	- dequeue a node from it and check if node equals destination
		- if yes, return the answer.
		- If no, put all the nieghbor nodes of the current node that is NOT visited already to the queue, update the distance to source parameter, distance + 1
	- Repeat


```Python
from collections import deque
def shortest_path(edges: list[list], source, destination) -> int:
	graph = buildGraph(edges)
	visited_nodes = set(source)
	queue = deque()
	queue.appned((source,0))
	while len(queue) > 0:
		node, distance = queue.popleft()
		if node == destination:
			return destination
		for neighbor in graph[node]:
			if not (neighbor in visited):
				visited.add(neighbor)
				queue.append((neighbor,distance+1))
	return -1
```

```Python
def find_shortest_path(graph, starting_node, goal):
    visited = []
    queue = [[starting_node]]
    while queue:
        path = queue.pop(0)
        node = path[-1]
        if node not in visited:
            neighbours = []
            for edge in graph.edges:
                if edge[0] == node:
                    neighbours.append(edge[1])
                elif edge[1] == node:
                    neighbours.append(edge[0])
            for neighbour in neighbours:
                new_path = list(path)
                new_path.append(neighbour)
                queue.append(new_path)
                if neighbour == goal:
                    return new_path
            visited.append(node)

    return []
```

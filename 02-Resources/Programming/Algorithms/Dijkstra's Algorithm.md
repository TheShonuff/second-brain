---
title: Dijkstra's Algorithm
Created: 2023-11-13 21:18
tags:
  - algorithms
aliases:
---
# Dijkstra's Algorithm
- An algorith that computes the shortest distance from a given vertex to the rest of the vertices in a graph.

>[!warning] Does not work on graphs with negative weight edges

- Runtime is $O(V+E)log V$
![[Pasted image 20231113212820.png]]
- Instantiate a dictionary that will eventually map vertices to their distance from the start vertex
- Assign the start vertex a distance of 0 in the min heap
- Assign every other vertex a distance of infinity in the min heap
- Remove the vertex with the smallest distance from the min heap and set that to the current vertex
- For the current vertex, consider all of its adjacent vertices and calculate the distance to them **(distance to the current vertex) + (edge weight of current vertex to adjacent vertex)**
- If this new distance is less than the current distance, replace the current distance.
- Repeat 4 and 5 until heap is empty
- After the heap is empty, return distances.

## Implementation
```Python
from heapq import heappop, heappush
from math import inf

graph = {
	'A': [('B', 10), ('C', 3)],
	'C': [('D', 2)],
	'D': [('E', 10)],
	'E': [('A', 7)],
	'B': [('C', 3), ('D', 2)]
}

def dijkstras(graph, start):
	distances = {}
	for vertex in graph:
		distances[vertex] = inf
	distances[start] = 0
	vertices_to_explore = [(o, start)]
	while vertices_to_explore:
		current_distance, current_vertex = heappop(veritces_to_explore)
		for neighbor, edge_weight in graph[current_vertex]:
			new_distance = current_distance + edge_weight
			if new_distance < distances[neighbor]:
				distances[neighbor] = new_distance
				heappush(vertices_to_explore, (new_distance, neighbor))
	return distances

distances_from_d = dijkstras(graph, 'D')
print("\n\nShortest Distance: {0}".format(distances_from_d))
```




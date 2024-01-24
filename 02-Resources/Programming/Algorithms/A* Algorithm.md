---
title: A* Algorithm
Created: 2023-11-18 21:35
tags:
  - algorithms
aliases:
---

---
# A* Algorithm
- Complexity is $O(b^d)$
- Rather than simply checking the distance up to the current vertex, we will check the distance up to the current vertex + the estimated distance from the current vertex to the end vertex.
	- This estimated distance is called the *heuristic*

>[!note] Sometimes refered to as [[Greedy Algorithms|Greedy Algorithm]] because it makes a locally optimal choice at every vertex.

- Ther are only a few important changes to make to [[Dijkstra's Algorithm]]
	- **add a target for the search** The new algorithm cannot optimiz with a *heuristic* unless it has a clear destination.
	- **Gather possible optimal paths and identify a signle shortest path**. You will find a path that has the shortest distance for the least cost.
	- **Implement a heurisitc that determines the likely distance remaining** The main difference is that this algorithm knows which to direction to head in.


## Time Complexity Explained
![[Pasted image 20231118215012.png]]
- $b$ is the brancing factor of the graph.
	- The average number of edges per vertex
	- The above example has **on average** 2 edges.
	- $b=2$
- $d$ is the depth of the goal vertex from the start vertex.
	- The goal vertex is 3 edges way.
	- $d=3$
- In the worst case, we would look at all the edges in the direction of the goal vertex until we reach the goal vertex. We would look at $b$ edges for every vertex in our search for close to $d$ iterations. $O(b^d)$

## Implementing the Heuristic

### Manhatan Heuristic
- To get this heuristic estimate we need to:
	- Measure the distance between the two vertices $x$ positional values and between their $y$ positional values.
	- Return the sum of the $x$ distance and $y$ distance togther.
		
```Python
def heuristic(start, target):
	x_distance = abs(start.position[0] - target.position[0])
	y_distance = abs(start.position[1] - target.position[1])
	return x_distance + y_distance
```

### Euclidean Heuristic
- Works off the Pythagorean theorem
- $\sqrt{xDistanc^2 + yDistance^2}$

```Python
def heuristic(start, target):
	x_distance = abs(start.position[0] - target.position[0])
	y_distance = abs(start.position[1] - target.position[1])
	return sqrt(x_distance * x_distance + y_distance * y_distance)
```
## Implementation
```Python
def a_star(graph,start):
	count = 0
	paths_and_distances = {}
	for vertex in graph:
		paths_and_distances[vertex] = [inf, [start.name]]
	paths_and_distances[start][0] = 0
	vertices_to_explore = [[0,start]]
	while vertices_to_explore and paths_and_distances[target][0] == inf:
		current_distance, current_vertex = heappop(vertices_to_explore)
		for neighbor, edge_weight in graph[current_vertex]:
			new_distance = current_distance + edge_weight + heuristic(neighbor+target)
			new_path = paths_and_distances[current_vertex][1] + [neighbor.name]

			if new_distance < paths_and_distances[neighbor][0]:
				paths_and_distances[neighbor][0] = new_distance
				paths_and_distances[neighbor][1] = new_path
				heappush(vertices_to_explore, (new_distace, neighbor))
				count += 1
	return paths_and_distances[target][1]
	
```

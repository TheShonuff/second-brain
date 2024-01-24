---
title: Python Graphs
Created: 2023-11-06 21:03
tags:
  - python
aliases:
---

---
# Python Graphs
- Perfect data structure for modeling network.
- Composed of **Node** and **Vertices**
- A graph can be represented by $G$ where $G=(V,E)$ 
	- $V$ is a set of vertices
	- $E$ is a set of Edges
- The higher the ratio of edges to vertices, the more connected the graph.
- When a graph is *weighted* there is a cost moving between vertices. 
	- When tallying the cost of a path, we add up the **total** cost of the edges used.
- **Directed Graphs** where edges restrict the direction of movement between vertices.
![[Pasted image 20231108233224.png]]
![[Pasted image 20231109212010.png]]
>[!note] We can move from *spikes* to *lasers*, but not from *lasers* to *spikes*
## Vocabulary
- **Vertex** also called a "node" is a fundamental part of the graph.
	- A *vertex* can have a name, referred to as a key
	- May also contain additional information called a *payload*
- **Edge** connectes two vertices to shwo that this is a relationship between them.
	- *Edges* may be one-way or two-way.
		- **Directed Graph** all the edges are one-way
- **Adjacent** When an edge exists between vertices.
- **Weight** may be weighted to show that there is a cost to go from vertex to another.
- **Path** in a graph is a sequence of vertices that are connected *edges*.
- **Cycle** in a directed graph is a path that starts and ends at the same vertex.
	- **Acyclic graph** a graph with no cycles
	- **Directed acyclic graph (DAG)** a directed with graph with no cycles.

## Graph Abstract Data Type
- `Graph()` creates a new, empty graph
- `addVertex(vert)` adds an instance of `Vertex` to the graph
- `addEdge(fromVert, toVert)` adds a new, directed edge to the graph
- `addEdge(fromVert, toVert, weight)` adds a new weighted, directed edge to the graph
- `getVertex(vertKey)` finds the vertex in the graph name `vertkey`
- `getVertices()` returns the list of all vertices in the graph
- `in` returns *True* for a statement of the form vertex in graph, if the given vertex is in the graph *False* otherwise
# Representing Graphs
- The vertex-edge relationship is represented in two ways.
	- Adjaceny list
	- Adjacent Matrix
![graphs gif](https://content.codecademy.com/programs/cs-path/graphs-conceptual/adjacency_matrix_2.gif)
## Adjacency Matrix
- easiest way to implement a graph is to use a two-dimensonal matrix.
- each rows and columns represent a vertex in the graph. 
	- The value stored in the cell at the intersection idicates there is an *edge*
- When two vertices are connected by an *edge* we say they are **adjacent**
- A value in a cell represents the weight of the *edge*
![](https://lh7-us.googleusercontent.com/v5QFKhHXbmHTHTnWqjAzbpRDbnFTiDu-oxxFug12N12JFUG8q-eWztiPnRKbDe5vVTjJpJ38eWOzdBueH488tJI36Y9be-IdgGvg91ut2lQTWWUWf00_Aou2OuVrKa4_6Hm4b_I4hgadXO8uXUt6KMJI6Q=nw)

## Adjacent List
- We keep a master list of all the vertices in the Graph object
- Each vertex object in the graph maintains a list of the other vertices that it is connected to.
![](https://lh7-us.googleusercontent.com/vtTOyHopOJdWyzmoFhrsCmV7_5jIb_yRVXNguSJMiuiOBkd6F_QBpnCDe8YgW051QVVHoIvT5aBSnCR6tXOxclcNmd4bmogl_rnp2W7un08jU5GnRNGzkAFebQ2K3JIFNeuW_PQZDCgOFC7mjAPFWG8ZyA=nw)

# Implementation
- Two classes make up the data structure. `Vertex` and `Graph`
- The functionality we require from these classes:
	- `Vertex` stores some data
	- `Vertex` stores the edges to connected vertices and their weight
	- `Vertex` can add a new edge to its collection
	- `Graph` stores all the vertices
	- `Graph` knows if it is directed or undirected
	- `Graph` can add a new vertex to its collection
	- `Graph` can add a new edge between stored vertices
	- `Graph` can tell whether a path exists between stored vertices.
## Vertex
```Python
class Vertex:
	def __inti__(self, value):
		self.value = value
		self.edges = {}
	def add_edge(self, vertex, weight=0)
		self.edges[vertex] = weight
	def get_edges(self):
		return self.edges.keys()
```

## Graph
```Python
class Graph:
	def __init__(self, directed = False):
		self.graph_dict = {}
		self.directed = directed
	def add_vertex(self,vertex):
		self.graph_dict[vertex.value] = vertex
	def add_edge(self, from_vertex, to_vertex, weight = 0):
		self.graph_dict[from_vertex.value].add_edge(to_vertex.value, weight)
		if not self.directed:
			self.graph_dict[to_vertex.value].add_edge(from_vertex.value, weight)
	def find_path(self, start_vertex, end_vertex):
		start = [start_vertex]
		seen = {}
		while len(start) > 0:
			current_vertex = start.pop(0)
			seen[current_vertex] = True
			print("Visiting " + current_vertex)
			if current_vertex == end_vertex
				return True
			else:
				vertices_to_visit = set(Self.graph_dic[currnet_vertex].edges.keys())
				start += [vertex for vertex in vertices_to_visit if vertex not in seen]
		return False
		
```
### Vertex
```Python
class Vertex:
	def __init__(self, key):
		self.id = key
		self.connectedTo = {}

	def addNeighbor(self, nbr, weight=0):
		self.connectedTo[nbr] = weight

	def __str__(self):
		return str(self.id) + " connectedTo: " + \
		str([x.id for x in self.connectedTo])
	def getConnections(self):
		return self.connecedTo.keys()

	def getId(self):
		return self.id

	def getWeight(self, nbr):
		return self.connectTo[nbr]
```

### Graph
```Python
class Graph:
	def __init__(self):
		self.vertList = {}
		self.numVertices = 0

	def addVertex(self, key):
		self.numVertices = self.numVertices + 1
		newVertex = Vertex(key)
		self.vertList[key] = newVertex
		return newVertex

	def getVertex(self, n):
		if n in self.vertList:
			return self.vertList[n]
		else:
			return None
	def __contains__(Self,n):
		return n inself.vertList

	def addEdge(self,f,t,weight=0):
		if f not in self.vertList:
			nv = self.addVertex(f)
		if t not in self.vertList:
			nv = self.addVertex(t)
		self.VertList[f].addNeighbor(self.verListp[t], weight)
	def getVertices(self):
		return self.vertList.keys()
	def __iter__(self);
		return iter(self.vertList.values())
```


## Traversal

### Breadth-first search
- vists all vertices in a graph $G$ that are $K$ edges away from the source vertex.
- Has a running time of $O(V+E)$  since every vertex and every edge will be checked once.
- Depending on the input to the graph, $O(3)$ could be between $O(1)$ and $O(V^2$)

#### Pseudocode
```
from collections import deque
def bfsPrint(graph: dict, source):
	q = deque(source)
	while len(q) > 0:
		current = q.popleft()
		print(currnet)
		for neighbor in grapph[current]
			q.append(neighbor)
```

### Depth-first search
- Starts at the root (top) node of a tree and goes as far as it can down a given branch (path), then backtracks until finds an unexplored path, and then explores it.
- Visits every vertex once and checs every edge in the graph once. $O(V+E)$

#### Python implementation
```Python
	def depth_first_search_recursive(graph, start, visited=None):
		if visited is None:
			visited = set()
		visited.add(start)
		for next in graph[start]:
			if next not in visited:
				dept_first_search_recursive(graph, next, visited)
		return visited
			
```
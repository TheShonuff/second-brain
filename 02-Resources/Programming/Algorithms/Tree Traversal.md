---
title: Tree Traversal
Created: 2023-11-08 20:30
tags:
  - algorithms
aliases:
---
# Tree Traversal
- Vertoces om a graph search include a "visited" list to keep track of whether or not each vertex has been checked.
- The run time for graph search algorithm is $O(V+E)$
- **DFS** employes recursion or stack data structure.
	- Helpful for determining whether a path exists between two points
- **BFS** relies on queue data structure. 
	- Helpful for finding the shortest path between two points.

## Breadth-first Search
- When you inspect every node on a level starting at the top of the tree and then move to the next level.
- Follows the [[Python Queues|Queue]] format of FIFO (First In, First Out)
![gif](https://static-assets.codecademy.com/Courses/CS102-Data-Structures-And-Algorithms/Breadth-First-Search-And-Depth-First-Search/Breadth-First-Tree-Traversal.gif)

## Depth-first Search
- Where you search deepin into a branch and don't move to the next until you've search until the end.

![depth first gif](https://static-assets.codecademy.com/Courses/CS102-Data-Structures-And-Algorithms/Breadth-First-Search-And-Depth-First-Search/Depth-First-Tree-Traversal.gif)


---
title: Greey Algorithms
Created: 2023-11-13 21:02
tags:
  - algorithms
aliases:
---

---
# Greedy Algorithms
- used in *optimization* problems.
- Common applications:
	- pathfinding
	- graph search
	- data compression

>[!tip] Just like greedy people, they only consider the choice that seems to be the best at the moment. Although it can be useful in some problems, a greedy algorithm does **NOT** always produce an optimal solution.

## When to use a greedy algorithm
- A problem that can be solved with a **greedy** algorithm *must* satisfy these two properties
	- **Optimal substructure property** The optimal solution for the problem contains optimal solutions to the sub-problems
	- **Greedy Property** The global optimal solution can be reached by making locally optimal solutions

### Advantages
- Greedy algorithms have the following advantages:
	- Easy to understand and implement
	- Time and space complexities are easy to analyze
	- Perform better than other paradigms like divide-and-conquer

### Disadvantages
- Most greedy algorithms fail to find the global optimal solution
- Hard to prove the correctness of a greedy algorithm



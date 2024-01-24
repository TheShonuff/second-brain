---
title: Heaps
Created: 2023-11-13 21:34
tags:
  - algorithms
aliases:
---
# Heaps
- A *concrete* data stucture.
	- priority queues are *abstract* data structures.
	- An abstract data strucutre determines the interface

>[!tip] In a **concrete** data structure defines the implementation

- Implements a priority queue as a complete binary tree.

- The are three rules that determine the relationship between the element at the index **k** and its surrounding children.
	- Its first child is at $2*K+1$
	- Its second child is at $2*K + 2*$
	- Its parent is at $(k-1) // 2$

>[!tip] An element must always be smaller than the elements that are twice its index plus one and twice its index plus two


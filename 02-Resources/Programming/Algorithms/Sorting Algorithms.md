---
title: Sorting Algorithms
creation date: 2022-12-03 22:09
aliases: 
tags:
  - cs
  - filed
  - algorithms
---

# Sorting Algorithms
Sorting is the process of rearraning the items in a collection so that the items are in some kind of order.
- Sorting numbers from smallest to largest
- Sorting name alphabetically
- Sorting movies based on release year

[Sorting Video](https://www.toptal.com/developers/sorting-algorithms)

Sorting is an incredibly common task. There are many different way to sort things  and different techniques have their own advantages and disadvantages.

## Quadratic Sorting Algorithms
These algorithms are all roughly equal.

| Algorithm      | Time Complexity **Best** | Time Complexity **Avg** | Time Complexity **Worst** | Space Complexity |
| -------------- | ------------------------ | ----------------------- | ------------------------- | ---------------- |
| [[Bubble Sort ]]   |  $O(n)$                    | $O(n^2)$                  | $O(n^2)$                   | O(1)             |
| [[Insertion Sort]] |  $O(n)$                       | $O(n^2)$                 | $O(n^2)$                   | O(1)             |
| [[Selection Sort]] |  $O(n)$                       | $O(n^2)$                  | $O(n^2)$                    | O(1)                 |

# Better Sorting
While the previous sorting alorgrithms can sort somewhat effiecently there are **faster** ways to sort data. This family of sorting algorithms can improve [[Time Complexity]] from $O(n^2)$ to $O(n log n)$. 

The trade is efficiency vs simplicity. There alogrithms are not as simple in nature.

[[Merge Sort]] 

| Algorithm      | Time Complexity **Best** | Time Complexity **Avg** | Time Complexity **Worst** | Space Complexity |
| -------------- | ------------------------ | ----------------------- | ------------------------- | ---------------- |
| [[Merge Sort]] | $O(nlogn)$               | $O(nlogn)$              | $O(nlogn)$                | $O(n)$           |
| [[Quick Sort]] | $O(nlogn)$               | $O(nlogn)$              | $O(n^2)$                  | $O(log n)$       |
| [[Radix Sort]] | $O(nk)$                  | $O(nk)$                 | $O(nk)$                   | $O(n+k)$                  |

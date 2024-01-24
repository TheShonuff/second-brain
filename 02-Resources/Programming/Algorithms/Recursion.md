---
title: Recursion
creation date: 2022-12-02 11:15
aliases: 
tags:
  - reading
  - cs
  - algorithms
---

# Recursion
- A process or a function that calls itself.

>[!note] Recursion means "defining a problem in terms of itself"

- The game plan is to invoke the same function with a different input until you reach the base case. which is the condition where the recursion ends.

## 3 Laws of Recursion
1. A algorithm must have a base case.
2. A algorithm must change its state and move toward the base case.
3. A algorithm must call itself, recursively.

>[!tip] A **return** is an important element in the recursion. We need some way to terminate the callstack. Otherwise a *stack overflow* occurs.

- A popular recursion example is the **Fibonacci** sequence. *F(i) = F(i-1) + F(i-2)*...
### Common Pitfalls
- no base case 
- wrong base case
- Forgetting to return
- returning the wrong element

>[!tip] Recursion is ideal for traversal of tree-like data structures
## Helper Method Recursion
- We have *two* functions. There's an outer function and an inner fuction within this model. The outer function calls and inner recursive function.

## Pure Recursion 
- For array's, use methods like slice, the spread operator, and concat that make copies of arrays so they're not mutated.
- Strings are immutable so methods like slice, substr or substring will need to be used to make copies
- To make copies of objects use Object.assign or the spread operator.

---
# Examples 
[[Python Recursion Examples]]
[[JavaScript Recursion Examples]]

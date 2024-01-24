---
title: Stacks
Created: 2023-09-25 20:13
tags:
  - algorithms
aliases:
---

---
# Stacks
- A **abstract data type** that represents a sequence of elements arranged according to a set of rules.
- Every queue provides operations for adding and removing elements in constant time $O(1)$
- There are two types of queues. **Last-in, First-out** and **First-in, First-out**
- Adding an elements can be referred to as **enqueue** operation.
- Retreiving an elements can be referred to as a **dequeue** operation.
- **Bounded Queues** have a fixed capacity.

>[!tip] First-in, first-out **FIFO**



## FIFO
- **First-in, First-out**
- Elements in the queue will be processed as a **first-come, first-served** basis.
- A new element is only allowed to join at the **tail**
- When an element leaves, followers shift exactly one position towards the **head**.
- **Note**: Think a grocey line queue or cars stopping at a stop light.

## LIFO 
- **Last-in, First-out**
- Elements that join and leave through only one end, the **top** is a LIFO queue.
- Common LIFO is the [[call stack]]

## Deque
- Allows enqueue or dequeue elements from both ends in constant time at any given time.
- Works as a **LIFO** or **FIFO** queue.

## Priority Queue
- maintains a sorted order
- lets new elements join where necessary while shuffling the existing elements around if needed.
- Note: Think about how boarding an airplane works. People with children or disablitieis are given priority to board the airplane first.
## Abstract Data Type
- `Stack()` creates a new stack that is empty
- `push()` add item to top
- `pop()` remove item from the top
- `peek()` return reference to top item.
- `isEmpty()` tests to see whether the stack is empty. returns a boolean
- `size()` returns the number of items on the stack. Returns an integer




- Good for reversing order
- good for matching up nested structures.



---
title: Computer Data Storage
creation date: 2022-11-28 10:36
aliases: 
tags:
  - reading
  - cs
  - algorithms
---

# Computer Data Storage

Array's are generally a **fixed-length** data collection type that lives in a section of memory with a physical hexademical address.

## Objects 
When you don't need ording, objects are an excellent choice.
Insertion - **O(1)**
Removal - **O(1)**
Searching -**O(n)**
Access - **O(1)**

## Fixed Array
- An ordered series of arrangement that is next to each other.
- Are typically given a **fixed length** when created. 
- start at a zero index
- The end of an array is (n-1) 
	- Segfault is accessing memory outside the bounds.
### Fixed Array Runtimes
Access - **O(1)**
Insert (Random) -  **O(n)**
Insert (Front) - **O(n)**
Insert (Back) - **O(1)**
Delete (Front) - **O(n)**
Delete (Back) - **O(1)**

>[!note] If any operation requires the array to shift positions it's O(n). Inserting at the end of the array is always constant O(1) as there requires no shifting of the array indexes or memory positions

Search (Unsorted) - **O(n)**
Search (Sorted) - ${\Large log_2n}$ 
Other sorts? - ${\large O(n \cdot log_n)}$

### Fixed Array Seach Sorted
Why is a sorted search ${\Large log_2n}$?  

Binary search algorithm.
$\Huge {Left + Right\over 2}$

First evulation wil look at the middle index and determine if the result is greater than or less than the parameter. If the result is less than the paramter that eleminates half of the array to search.

## Circular Array
 - Creates efficency on adding to the front of an array.
 - creates additional complexity
 
One of the problems with a typical fixed-length array is that we can reach O(n) whenever we try inserting or deleting from the front of the array. All the elements within the array need to be shifted. The **circular array** attempts to improve this time complexity. 

To establish a **circular array** we create two pointers. A *start* pointer and an *end* pointer. These pointers are adjusted whenever an element is added or deleted.

![[Pasted image 20221202104542.png]]

If we have some data at buff[0] that we wanted to deleted. We moved the *start* pointer to buff[1]


 > [!note] We use the modulo operator % to get the remainder
 
 - Array length is mod. 
 - Adding to the end is  x[(front -1) % 10]

## Dyanmic Array
Allows for the expansion of an array whenever the collection is filled up. The best practice is to double the size of the array as opposed to adding a single block. 
- **logical size** - is how many pieces of data are actually allocated in the array
- **Physical size** - The size of the array itself.
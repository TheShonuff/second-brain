---
title: Max Diff - Easy
creation date: 2022-12-24 23:39
aliases: []
tags: codewars 
---
# Max Diff - Easy
You must implement a function that returns the difference between the larges and smallest value in a given list/array receieved as the parameter
- List contains integers, that means it may contain some negative numbers
- If list is empty or contains a single element, return 0
- The list is not sorted

**Success**:: true

### Solution
```Rust
fn max_diff(numbers: &[i32]) -> i32 {
	if numbers.len() == 0 || numbers.len() == 1 {
		0
	} else {
		let min = numbers.iter().min().unwrap();
		let max = numbers.iter().max().unwrap();
		max - min
	}
}
```

**Notes**:: This was an easy problem to solve. Using the min and max methods I iterated over the supplied unsorted list I found the min and max and then found the difference. I messed up on the inital reading and used a filter to git rid of any 0 values.

```Rust
fn max_diff(numbers: &[i32]) -> i32 {
	
}
```
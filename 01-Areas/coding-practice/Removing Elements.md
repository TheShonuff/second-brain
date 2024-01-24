---
title: Removing Elements
creation date: 2022-12-18 21:25
aliases: []
tags: codewars arrays
---
# Removing Elements
Take an array and remove every second element from the array. Always keep the first element and start removing with the next element

**Success**:: true

### Solution
```Rust 
fn remove_every_other(arr: &[u8]) -> Vec<u8> {
	let mut vec: Vec::<u8> = Vec::new();
	for x in arr.iter().step_by(2) {
		vec.push(*x);
	}
	vec
}
```

**Notes**:: Ran through a couple of different versions fighting the compiler. I orginally wanted to use the step method but later found step_by is included in the standard library and didn't need to use an external crate itertools. Then I fould with getting the elements of the iteration to collect into the revelant collection. ultimately i used a for loop to iterate the array and push the elements in a created mutable array.

### Best Solution
```Rust
fn remove_every_other(arr: &[u8]) -> Vec<u8> {
	arr.iter().step_by(2).copied().collect()
}
```
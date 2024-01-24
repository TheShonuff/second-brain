---
title: Find Multiples of a Number
creation date: 2022-12-23 21:21
aliases: []
tags: codewars 
---
# Find Multiples of a Number
In this simple exercise, you will build a program that takes a value, **integer**, and returns a list of its multiples up to another value, **limit**. If **limit** is a multiple of **integer**, it should be included as well. There will onyl ever be positive integers pased into the function, not consisting of 0. The limit will always be higher than the base.

**Success**:: true

### Solution
```Rust
fn find_multiples(n:u32, limit: u32) -> Vec<u32> {
	(n..=limit).into_iter().filter(|x| x % n == 0).collect()
}
```

**Notes**:: A simple exercise that I nearly got. Still have trouble will implementing the filter method. Intially i reached for the map method, but the filter has the predicate to test each element in the array and then collects it into the array based on its return. I also didn't include the limit integer into the solution which used up acouple of test cases.

### Best Solution
```Rust
fn find_multiples(n:u32, limit: u32) -> Vec<u32> {
	(n..=limit)
		.step_by((n) as usize)
		.collect()
}
```
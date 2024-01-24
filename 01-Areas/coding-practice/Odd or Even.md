---
title: Odd or Even
creation date: 2022-12-21 23:56
aliases: []
tags: codewars rust arrays
---
# Odd or Even
Given a list of integers, determine whether the sum of its elements is odd or even. Give your answer as string matching "odd" or "even". If the input array is empty consider it as [0] (array with a zero).

**Success**:: true

### Solution
```Rust
fn odd_or_even(numbers: Vec<i32>) -> String {
	let result: i32 = numbers.into_iter().sum();
	let x = if let 0 =  result % 2 {
		"even"
	} else {
		"odd"
	};
	x.to_string()
}
```

**Notes**:: This was an easy one. Take the sum of all the elements of the array. My solution would have been more idiomatic using a match statement.

### Best Solution
```Rust
fn odd_or_even(numbers: Vec<i32>) -> String {
	match numbers.iter().sum::<i32>() % 2 == 0 {
		true => "even".to_string(),
		false => "odd".to_string()
	}
}
```
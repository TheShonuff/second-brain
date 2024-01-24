---
title: Sum of Minimums
creation date: 2022-12-23 22:28
aliases: []
tags: codewars 
---
# Sum of Minimums
Given a 2D(nested) list of m * n , your task is to find the sum of the minimum values in each row.

**Success**:: true

### Solution
```Rust
sum_of_minimums(numbers: [[u8;4]];4) -> u8 {
	let mut result = 0;
	for x in 0..numbers.len() {
		result += numbers[x].inter().min().unwrap();
	}
	result
}
```

**Notes**:: The direction i initally headed down was close but wrong. We need to get each element, an array, in the list and then iterate through each to get the minimum value. Then add the value to the result.

### Best Solution
```Rust
sum_of_minimums(numbers: [[u8;4]];4) -> u8 {
	numbers.iter().map(|row| row.iter().min.unwrap()).sum()
}
```
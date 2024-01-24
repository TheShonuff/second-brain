---
title: Maximum Product
creation date: 2022-12-25 00:32
aliases: []
tags: codewars 
---
# Maximum Product
Given an array of integers, Find the maximum product obtained from multiplying 2 adjacent numbers in the array.

**Success**:: true

### Solution
```Rust
fn adjacent_elemtns_product(xs: &[i32]) -> i32 {
	let result = xs.iter().clone().min().unwrap();
	let mut val = result.clone;
	for x in xs.windows(2) {
		let product = x[0] * x[1]
		if product > val {
			val = product
		}
	}
	val
}
```

**Notes**:: This one got me stumped due to a lifetime error. I still haven't figured that one out but I managed to get this to work by cloning the results of **result** into val. Then I iterate over the referenced array and multiply the adjacent elements in a window of 2. If the value is greater then the starting minimum value then make it the new **val**.

### Best Solution
```Rust
fn adjacent_elements_product(xs: &[i32]) -> i32 {
	xs.windows(2).map(|x| x[0] * x[1]).max().unwrap()
}
```
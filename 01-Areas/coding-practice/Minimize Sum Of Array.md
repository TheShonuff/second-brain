---
title: Minimize Sum Of Array
creation date: 2023-01-11 00:34
aliases: []
tags: codewars 
---
# Minimize Sum Of Array
Given an array of integers, **find the minimum** sum which is obtained from summing each two integers product.

*A list will contain positives only*
*A list will always have an even size*

**Success**:: true

### Solution
```Rust
fn min_sum(xs: &[u64]) -> u64 {
    let mut position = xs.len() - 1;
    let count_to = xs.len() / 2;
    let mut accumulator: u64 = 0;
    let mut sort = Vec::from_iter(xs.into_iter().cloned());
    sort.sort();
    for x in 0..count_to {
        accumulator += sort[x] * sort[position];
        position -= 1;
    }
    accumulator 
}
```

**Notes**:: Certainly not idiomatic. The goal was to find a way to iterate through the list and multiply the current min and max numbers. I realized this was possible through a sorted list. The list being only even number I had to iterate one size going up and the other side going down. Therefore I could achieve the min / max. 

### Best Solutions
```Rust
fn min_sum(xs: &[u64]) -> u64 {
	let mut xs = xs.to_vec();
	xs.sort;

	let maxs = &xs[xs.len() /2..];
	let mins = &xs[..xs.len()/2];

	maxs.iter()
		.zip(mins.iter().rev())
		.map(|(max,min)| max * min))
		.sum()
}
```

---
title: Maximum Triplet Sum
creation date: 2022-12-31 01:28
aliases: []
tags: codewars 
---
# Maximum Triplet Sum

Given an array/list of n integers, find the maximum triplet sum in the array **without duplication**

**Success**:: true

### Solution
```Rust
fn max_tri_sum(arr: &[i32]) -> i32 {
    let mut vec = arr.to_vec();
    vec.sort();
    vec.dedup();
    vec.windows(3).map(|x| x[0] + x[1] + x[2]).max().unwrap() 
}
```

**Notes**:: This one took me a few minutes, or hour, to figure out how to manipulate the array correctly. My original though was close to the oneliner best solution solution but I needed to get there myself. I was very close to giving in on this one. Using itertools I could have chained sorteed, rev, dedup.

### Similar to mine
```Rust
fn max_tri_sum(xs: &[i32]) -> i32 {
	let mut xs = arr.to_vec();
	xs.sort();
	xs.dedup();
	xs.iter().rev().take(3).sum()
```

### Best Solution
```Rust
use itertools::Itertools

fn max_tri_sum(xs: &[i32]) -> i32 {
	xs.iter().sorted().rev().dedup().take(3).sum()
}
```
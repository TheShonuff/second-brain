---
title: N-th Power
creation date: 2022-12-31 14:52
aliases: []
tags: codewars 
---
# N-th Power
You are given an array with positive numbers and a non-negative number N. You should find the N-th power of the element in the array with the index N. If n is outside of the array, then return -1. Don't forget that the first element has the index 0


**Success**:: true

### Solution
```Rust
fn index(nums: &[u64], n: usize) -> Option<u64> {
   if nums.len() <= n {
       return None
   } else {
       Some(nums[n].pow(n as u32))
   } 
}
```

**Notes**:: This one was a slight head scratcher as I haven't really explored options. 

### Best Solutions

```Rust
fn index(nums: &[u64], n: usize) -> Option<u64> {
	nums.get(n).map(|x| x.pow(n as u32))
}
```

```Rust
fn index(nums: &[u64], n: usize) -> Option<u64> {
	match nums.get(n) {
		Some(i) => {return Some(i.pow(n as u32));}
		None => {return None;}
	}
```
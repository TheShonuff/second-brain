---
title: Moving Zeros To The End
creation date: 2022-12-26 01:23
aliases: []
tags: codewars 
---
# Moving Zeros To The End
Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

**Success**:: true

### Solution
```Rust
fn move_zeros(arr: &[u8]) -> Vec<u8> {
	let mut zero_vec = Vec::new();
	let mut num_vec =  Vec::new();
	for (i,x) in arr.iter().enumerate() {
		if arr[i] != 0 {
			num_vec.push(arr[i])
		} else {
			zero_vec.push(arr[i])
		}
	}
	for x in zero_vec {
		num_vec.push(x)
	}
	num_vec
}
```

**Notes**:: This was an easy 5 kyu which I don't think I got credit for...

### Best Solution
```Rust
fn move_zeros(xs: &[u8]) -> Vec<u8> {
	let mut ys - Vec::with_capacity(xs.len());
	ys.extend(xs.iter().filter(|&&x| x != 0));
	ys. resize(xs.len(), 0);
	ys
}
```
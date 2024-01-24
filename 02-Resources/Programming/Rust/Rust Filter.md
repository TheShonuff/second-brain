---
title: Rust Filter
creation date: 2022-12-13 01:10
aliases: []
tags: rust iterator/adapter
---

# Rust Filter
- A library for creating predicates and filter for use with the **Iterator::filter**
- Can be combined with **AND OR NOT**

```Rust
let numbers: Vec<i32> = vec![ 10,20,30,40,50,60,70,80];

let even_number = numbers
	.into_iter()
	.filter(|n| n % 2 == 0)
	.collect:<Vec<_>>();

println!("{:?}". even_number);
```

```Rust
let words = vec!["autobot", "beach", "car", "decepticon", "energon", "frothy"];

let transformed: Vec<_> = words 
	.int0_iter()
	.filter(|word| !word.contains("h"))
	.map(|word| word.to_uppercase())
	.collect();

println!("{:?}", transformed);
```

# Source 
[Delfstack](https://www.delftstack.com/howto/rust/rust-filter/)




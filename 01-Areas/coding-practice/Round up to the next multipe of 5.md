---
title: Round up to the next multipe of 5
creation date: 2022-12-16 00:39
aliases: []
tags: codewars mathematics
---
# Round up to the next multipe of 5
Given an integer as input, can you round it to the next multiple of 5?

**Success**:: true

### Solution
```Rust
fn round_to_next_5(n: i32) -> i32 {
	let num: f64 = ((n as f64)/5.0).ceil();
	(num * 5.0) as i32
}
```

**Notes**:: This one had me thinking at first. Then i realized that in order for this to work we would have to divide the supplied number by 5, round the decimal value up to the nearst whole number using **.ceil( )** then multiply that result by 5 to find the closed multiple of 5.

### Best Solution
```Rust
fn round_to_next_5(n: i32) -> i32 {
	n + (5 - n % 5) % 5
}
```

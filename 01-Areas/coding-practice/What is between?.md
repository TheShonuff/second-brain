---
title: What is between?
creation date: 2022-12-18 20:36
aliases: 
tags:
  - codewars
---
# What is between?
Complete the function that takes two integers (a,b) where  (a < b) and return an array of all integers between the input parameters, including them.

**Success**:: true

### Solution
```Rust
fn between(a:i16, b:i16) -> Vec<i16> {
	let mut vec = Vec::new();
	for x in a..=b {
		vec.push(x);
	}
	vec
}
```

**Notes**:: Simple problem that uses a for loop to iterate between the values and adds them to an vector. There is a more idiomatic solution that uses the [collect](https://doc.rust-lang.org/stable/std/iter/trait.Iterator.html#method.collect) that can take anything iterable and turn it into a revelant collection.

### idiomatic solution
```Rust
fn between(a:i16, b:i16) -> Vec<i16> {
	(a..=b).collect()
}
```
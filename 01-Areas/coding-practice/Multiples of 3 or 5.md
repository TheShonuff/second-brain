---
title: Multiples of 3 or 5
creation date: 2022-12-22 01:04
aliases: []
tags: codewars mathematics
---
# Multiples of 3 or 5
Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in. Additionall, if the number is negative, return 0.

**Success**:: true

### Solution
```Rust
fn solution(num: i32) -> i32 {
	let mut result: i32 = 0;
	if result < 0 {
		return result
	}
	for x in 0..num {
		if x % 3 == 0 || x % 5 == 0 {
			result += x
		}
	}
	result
}
```

**Notes**:: This was an easy level 6 kata. I only messed up the part where it was below the supply number. My initial solution included the supplied number. The more elegant solution used a .filter( ) method and sum( )

### Best Solution
```Rust
fn solution(num: i32) -> i32 {
	(i..num).filter(|x| x % 3 == 0 || x % 5 == 0).sum()
}
```
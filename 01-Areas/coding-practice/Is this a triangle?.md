---
title: Is this a triangle?
creation date: 2022-12-18 14:26
aliases: []
tags: codewars mathematics
---
# Is this a triangle?
Implement a function that accepts 3 integer values a,b,c. The function should return true if an triangle can be build with the sides of given length and false in any other case.

**Success**:: true

### Solution
```Rust
fn is_triangle(a: i64, b: i64, c: i64) -> bool {
	if (a + b <= c) || (a + c <= b) || (b + c <= a){
		false
	} else {
		true
	}
}
```

**Notes**:: A trianlge is valid if the sum of any 2 sides is greater than the third. I initially got my conditional reveresed. This was partially because I cheated and saw the conditional setup on geeks 4 geeks. 

### Best Solution
```Rust
fn is_triangle(a: i64, b: i64, c: i64) -> bool {
	a + b > c && a + b > b && b + c > a
}
```

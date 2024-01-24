---
title: Sum of Angles
creation date: 2022-12-14 23:59
aliases: []
tags: codewars 
---
# Sum of Angles
Find the total sum of internal angles (in degrees) in an n-sided simple polygon. N will be greater than 2

**Success**:: true

### Solution
```Rust
fn angle(n: u32) -> u32 {
	(n-2) * 180
}
```


**Notes**:: Pretty silly this is a level 7 kyu problem. If we couldn't search for the solution of the problem than yeah this would have been harder. A quick search reveal the formula is n-2 * 180...
---
title: Find Nearest Square Number
creation date: 2022-12-31 00:01
aliases: []
tags: codewars 
---
# Find Nearest Square Number

Your task is to find the nearest square nummber.

**Success**:: false

### Solution
```Rust
fn nearest_sq(n: u32) -> u32 {
	((n as f64).sqrt().round() as u32).pow(2)
}
```


**Notes**:: The solution is so obvious after you look at it. Square the number. Round down. Then raise it to the power of 2..
---
title: Fake Binary
creation date: 2022-12-15 11:30
aliases: []
tags: codewars array string
---
# Fake Binary
Given a string of digits, you should replace any digit below 5 with "o" and any digit 5 and above with '1'. Return the resulting string.

**Success**:: true

### Solution
```Rust 
fn fake_binary(s: &str) -> String {
	let mut vec: Vec<_> = s.chars().collect();
	let mut result = Vec::new();
	for x in vec.iter() {
		if x.to_digit(10) > Some(5) {
			result.push('1')
		} else {
			result.push('0')
		}
	}
	result.into_iter().collect()
}
```

### Best Solution
```Rust
fn fake_bin(s: &str) -> String {
	s.chars().map(|c| if c < '5' {'0'} else {'1'}).collect()
}
```

**Notes**:: Fought the compiler for a bit on this one. Struggled comparing the chars to an integer value. I wanted to implement in the map function initally but my brain for some reason can implement it. Seeingi the **Best Solution** the answer was so obvious. I was able to successfully implement see the the into_iter().collect() converted the vector of chars into an integer. I'm not sure entirely how or why that's done. 
---
title: Switcheroo
creation date: 2022-12-20 10:59
aliases: []
tags: codewars strings
---
# Switcheroo
Given a string made up of letters a b, and/or c, switch the positions of letter a and b( change a to b and vice versa). Leave any incidence of c untouched.

**Success**:: true

### Solution
```Rust
fn switcheroo(s: &str) -> String {
	let mut result = String::new();
	for letter in s.chars(){
		if letter = 'a'{
			result.push_str("b")
		} else if letter = 'b' {
			result.push_str("a")
		} else {
			result.push_str(&letter.to_string());
		}
	}
	result
}
```

**Notes**:: This was an easy one. I simply had to iterate over the supplied string slice and change each element that matched my condition. I had to look up chaging char to &str but I already knew to use **.to_string( )** I simply forgot. I believe this can be made more idiomatic using a match statement.

### Best Solution
```Rust
fn switcheroo(s: &str) -> String {
	s.chars().map(|e|
		match e {
			'a' => 'b',
			'b' => 'a',
			_ => e,
		}
	).collect()
}
```
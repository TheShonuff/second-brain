---
title: Alternating Case
creation date: 2022-12-18 15:23
aliases: []
tags: codewars strings
---
# Alternating Case
Define a function such that each lowercase letter becomes uppercase and each uppercase letter becomes lowercase.

**Success**:: true

### Solution
```Rust
fn to_alternating_case(s: &str) -> String {
	let mut x = String::new();
	for mut letter in s.chars(){
		if letter == letter.to_ascii_uppercase(){
			x.push_str(&letter.to_string().to_lowercase());
		} else {
			x.push_str(&letter.to_string().to_lowercase());
		}
	}
	return x.to_string()
}
```

**Notes**:: My intial instinct was to make this a inter() with a map and try to conditionaly change the char based on upper or lower case. After a little while the for loop became a better option. The next trick was to get the changed letter into a string. I was able to change the letter but unable to publish the results of the change. I created a new empty string that we could pust the new char into. My solution works but looking at the "best" solution I see they used the [extend method](https://doc.rust-lang.org/std/iter/trait.Extend.html).
> [!note] The extend a collection the contents of an iterator

### Best Solution
```Rust
fn to_alternating_case(s: &str) -> String {
	let mut result = String::with_capacity(s.len());
	for c in s.chars(){
		if c.is_uppercase(){
			result.extend(c.to_lowercase())
		} else {
			result.extend(c.to_uppercase())
		}
	}
	result
}
```
---
title: Get The Middle Character
creation date: 2022-12-14 00:20
aliases: []
tags: codewars strings
---
# Get The Middle Character
You are going to be given a word. Your job is to return the middle character of the word. If the word's length is odd, return the middle character. If the word's length is even, return the middle 2 characters.

**Success**:: true

### Solution
```Rust
fn get_middle(s: &str) -> &str {
	if s.len() % 2 == 0 {
		let mid = s.len() / 2;
		return &s[mid..mid + 2];
	} else {
		let mid = s.len() / 2;
		return &s[mid..mid + 1];
	}
}
```

### Best Solution
```Rust
fn get_middle(s:&str) -> &str {
	&s[s.len()-1/2..s.len()/2+1]
}
```

**Notes**:: This took me a minute to figure out how to manipulate and iterate over the string. The best solution is really elegant one liner but I'm happy with my solution even though it's not idiomatic. 
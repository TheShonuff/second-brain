---
title: Vowel Count
creation date: 2022-12-22 01:34
aliases: []
tags: codewars strings
---
# Vowel Count
Return the number (count) of vowels in the given string.

**Success**:: true

### Solution
```Rust
use regex::Regex;

fn get_count(string: &str) -> usize {
	let mut vowels_count: usize = 0;
	for vowel in Regex::new(r"[aeiou]").unwrap.find_iter(string){
		vowels_count += 1;
	}
	vowels_count
}
```

**Notes**:: A good use of regex here. There is a more idiomatic solution using match

### Best solution
```Rust
fn get_count(string: &str) -> usize {
	string.matches(|x| match x {'a'|'e'|'i'|'o'|'u' => true, _ => false}).count()
}
```
---
title: Fix String Case
creation date: 2022-12-14 23:44
aliases: []
tags: codewars 
---
# Fix String Case
In this kata, you will be given a string that may have mixed uppercase and lowercase letters and your task is to convert to either lower case or uppercase only base on:
- If the string contains equal number of uppercase and lowercase letter, convert the string to lowercase.
- make a few changes as possible

**Success**:: true

### Solution
```Rust
fn solve(s: &str)->String {
	let mut map = std::collections::HashMap::new();
	for letter in s.chars() {
		if letter == letter.to_ascii_uppercase() {
			let count = map.entry(String::from("Upper")).or_insert(0);
			*count += 1;
		} else {
			let count = map.entry(String::from("Lower")).or_insert(0);
			*count += 1
		}
	}
	if map.get("Upper") > map.get("Lower") {
		return s.to_string().to_uppercase();
	} else {
		return s.to_string().to_lowercase();
	}
}
```


**Notes**:: My initial thought was to create an [[Frequency Counter]] and count the number of instances of upper case characters and lowercase characters. Then compare the 2 values and output the string to the proper output. My solution doesn't feel idiomatic but it got the job done. A more idiomatic approach appears to be just count the number of upper case characters and subtract from the string length total.

### Best Solution
```Rust
fn solve(s: &str) -> String {
	let upper_chars = s
		.matchs(|ch:char| ch.is_uppercase())
		.count();
	let lower_chars = s.len() - upper_chars;
	if upper_chars > lower_chars {
		s.to_uppercase()
	} else {
		s.to_lowercase()
	}
}
```
---
title: Spacify
creation date: 2022-12-23 20:54
aliases: []
tags: codewars strings arrays
---
# Spacify
Modify the spacify function so that it returns the given string with spaces inserted between each character.

**Success**:: true

### Solution
```Rust
fn spacify(s: &str) -> String {
	Regex::new(r"[a-zA-z ]")
        .unwrap()
        .find_iter(s)
        .map(|x| x.as_str())
        .collect::<Vec<_>>()
        .join(" ")
}
```

**Notes**:: This was another good use case for regex. My first attempt with out regex inserted a space at the end which wasn't an ideal solution. I needed a way to complete the string without adding the " " to the end. I used a recently completed kata as a basis to build my regex and iterate through the given string and collect my results. Using the crate "itertools" would have simplifed the solution significantly. 

### Best Solution 
```Rust
use itertools::Itertools;


fn spacify(s: &str) -> String {
	s.chars().join(" ")
}
```


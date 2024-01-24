---
title: Counting Duplicates
creation date: 2022-12-28 11:07
aliases: []
tags: codewars 
---
# Counting Duplicates

Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occure more than once in the input string. The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.

**Success**:: true

### Solution
```Rust
fn count_duplicates(text: &str) -> u32 {
    let mut map = std::collections::HashMap::new();
    let mut dups: u32 = 0;
    for x in text.chars() {
        let count = map.entry(x.to_string().to_lowercase()).or_insert(0);
        *count += 1;
    }
    for (_key, value) in map {
        if value > 1 {
            dups += 1
        }
    }
    dups
}
```

**Notes**:: Counting duplicates was easy with implementing a hashmap. It appears the best solution also used a hashmap in their solution. I was only trip up in not formating the input to the hashmap as an always lower. My first attempt was wrong due to my hashmap tracking lower and upper case as a different instance. 

### Best Solution
```Rust
use std::collection::HashMap;

fn count_duplicates(text: &str) -> u32 {
	let mut char_count: HashMap<char, u32> = HashMap::new();
	for c in text.to_lowercase().chars() {
		let mut e = char_count.entry(c).or_default();
		*e += 1;
	}
	char_count.values().filter(|&&v| v > 1).count() as u32
}
```
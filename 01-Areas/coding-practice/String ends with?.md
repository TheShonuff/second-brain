---
title: String ends with?
creation date: 2022-12-17 01:08
aliases: []
tags: codewars strings
---
# String ends with?
Complete the solution so that it returns true if the first argument, string, passed in ends with the 2nd argument, also a string.

**Success**:: true

### Solution
```Rust
fn solution(word: &str, ending: &str) -> bool {
	word.ends_with(ending)
}
```

**Notes**:: Because I didn't copy paste the solution I used words instead of word and missed the 1 attempt victory.... This almost felt like cheating. For variation I added another solution that adds more features.

### Another solution
```Rust
fn solution(word: &str, ending: &str) -> bool {
	if word.len() < ending.len() {
		return false;
	}
	&word[word.len()-ending.len()..] == ending
}
```

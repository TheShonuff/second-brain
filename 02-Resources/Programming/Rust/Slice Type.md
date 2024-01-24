---
title: Slice Type
creation date: 2022-12-05 23:45
aliases: []
tags: rust filed
---

# Slice Type
**Slices** let you reference a contigous sequence of elements in a collection rather than the whole colleciton.

## String Slice
A *string slice* is a reference to part of a [[Rust Strings|string]] 
```Rust
let s = String::from("Hello World");

let hello = &s[0..5];
let world = $s[6..11];
```
Slices are created using a range within brackets. From starting index..ending index.
![Slices](https://doc.rust-lang.org/book/img/trpl04-06.svg)
Another way to write slices
```Rust
let s = String::from("hello");
let len = s.len();
let slice = $s[0..len]
let slice = $s[..]
```

### Example
Write a function that takes a string of words separated by spaces and returns the first word it finds in that string. If the function doesn’t find a space in the string, the whole string must be one word, so the entire string should be returned.
```Rust
fn first_word(s: &String) => &str {
	let bytes = s.as_bytes();
	for(i &item) in bytes.iter().enumerate(){
		if item == b' ' {
			return &s[0..i];
		}
	}
	&s[..]
}
```

## Slice The Array
Slices can be performed on array's.
```Rust
let a = [1,2,3,4,5];
let slice = &a[1..3];
```
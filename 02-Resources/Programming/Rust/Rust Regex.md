---
title: Rust Regex
creation date: 2022-12-21 00:03
aliases: []
tags: rust regex
---

# Rust Regex

```Rust
fn main() {
	let regex = Regex::new(r"\d{3}").unwrap();
	let a: &str = "123bbasfsdf23asd2021-06-1&";
}
```

The **r** in front of the regex expression allows the elimation of backslashes.

- There is no [[Match]] function. 

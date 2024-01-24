---
title: Rust Iterators Windows
creation date: 2022-12-24 15:15
aliases: 
tags:
  - reading
  - iterators
  - windows
  - rust
---

# Rust Iterators Windows
Iterate over a slice with a window of a specified size.

[Doc.rust.lang](https://doc.rust-lang.org/std/slice/struct.Windows.html)

```Rust
let slice = ['w', 'i', 'n' , 'j', 'l'];
for window in slice.windows(2) {
	println!("[{}, {}]", window[0], window[1])
}
```




---
title: Rust Implementation
creation date: 2022-12-20 00:12
aliases: []
tags: rust impl filed
---

# Rust Implementation
The **impl** keyword in Rust is used to implement some functionality on types. There are two main kind of implementations in Rust:
1. Inherent Implementation
	- Tied to a single concrete *self*
	- These *self* implementations are **always** in scope.
2. [[Traits|Trait]] Implementation
	- Abstract definition of shared behaivor amongst different types.
	- Can access other methods within a trait.
	- Uses the *for* keyword.

> [!note] each [[Structs|struct]] is allowed to have multiple impl blocks.

The follow are equivalent
```Rust
impl Rectangle {
	fn area(&self) -> u32 {
		self.width * self.height
	}
}

impl Rectangle {
	fn can_hold(&self, other: &Rectangle) -> bool {
		self.width > other.width && self.height > other.height
	}
}
```

```Rust
impl Rectangle {
	fn area(&self) -> u32 {
		self.width * self.height
	}
	fn can_hold(&self, other: &Rectangle) -> bool {
		self.width > other.width && self.height > other.height
	}
}
```
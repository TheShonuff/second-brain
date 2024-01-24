---
title: Rust If Let
creation date: 2022-12-07 10:37
aliases: []
tags: reading rust filed
---

# Rust - If Let
The **if let** lets you combine **if** and **let** into a less verbose way to handle values that match one pattern while ignoring the rest.

>[!note] typically used with [[Enums]]

Instead of using the underscore in [[Match]] as a catch-all we have another way to write this kind of control flow.
```Rust
let config_max = Some(3u8);
if let Some(max) = config_max {
	println!("The maximum is configured to be {}", max);
}
```

The **if let** syntax takes a pattern and an expression separated by an *equal sign*.

>[!note] While **if let** is less typing and boilerplate we do lose a lot of the exhaustive checking that [[Match]] enforces. 

> [!tip] **If let** is just syntax sugar

## Else 
- If a pattern doesn't match nothing will happen
- Including an **else** allows for an event when the pattern doesn't match.

## Syntax
```Rust
if let(value1,value2) = match_expression {
	statement1;
} else {
	statement2;
}
```

### Example
```Rust
fn main() {
	let gfg = ("Geeks", "for", "Geeks");
	if let ("Geeks", "for", "Geeks") = gfg {
		println!("Pattern matched")
	} else {
		println!("Pattern does not match")
	}
}
```


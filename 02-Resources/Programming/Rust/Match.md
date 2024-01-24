---
title: Match
creation date: 2022-12-07 10:36
aliases: []
tags: rust filed
---

# Match
A control flow construct.

> [!note] Typically used with [[Enums]]

Similar to the **if** statment but there's a big difference. The **if** expression needs to return a boolean. If true then. The **match** can return any type. These are called *match arms*.

Match arms have 2 parts and then seperated by a comma.
1. A pattern
2. some code

>[!note] if curly brackets are using within a match for multiple lines. *the comma is optional* following the line.

>[!warning] Arms must account for **all** possiblites

The underscore _ is the catch-all in the match arms.
```Rust
let dice_roll = 9;
match dice_roll {
	3 => add_fancy_hat(),
	7 => remove_fance_hat(),
	_ => reroll(),
}

fn add_fancy_hat(){}
fn remove_fancy_hat(){}
fn reoll(){}
```

## Matching with Option\<T\>
A function that if there's a value inside will add one. Otherwise it will not attempt to perform any operations.
```Rust
fn plus_one(x: Option<i32>) -> Option<i32> {
	match x {
		None => None,
		Some(1) => Some(i + 1),
	}
}

let five = Some(5);
let six = plus_one(five);
let none = plus_one(None);
```

### Example
```Rust
pub fn str_str(haystack: String, needle:String) -> i32 {
	let result = match haystack.find(&needle) {
		None => -1,
		Some(i) => i as i32
	}
	result
}
```
> [! note] Assign the match condition to a variable.


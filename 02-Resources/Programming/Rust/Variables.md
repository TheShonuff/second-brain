---
title: Variables
creation date: 2022-11-20 21:02
aliases: [rust variables]
tags: reading rust filed
---

# Variables
The rust syntax is a brace syntax very similar to javascript. There are also two ways to declare variables using **let** and **const**.

## let
1. Variables declared with let a immutable by default
2. Variables can be made mutable with the **mut** keyword.
3. let mut -- is an example of declaring a mutable variable.

**let** allows for multiple variable declartions through destructering.

```rust
fn main() {
	let (bunnies, carrots) = (8, 50) 
}
```

## const
1. Const variables are **always** immutable.
2. A type **must** be decalred when defining a const variable.
3. Const variables can be declared in any scope
4. Const variables may only be set to a constant expression, not a result of a value that could only be computed at runtime.



# Shadowing Variables
You can declare a new variable with the same name as a previous variable. The first variable would be *shadowed* by the second. Which takes use of the first variable until end of scope or itself is *shadowed*.

```rust 
fn main() {
	let x = 5;
	let x = x + 1;

	{
		let x = x * 2;
		println!("The value of x in the inner scope is: {x}");
	}
	println!("the value of x is: {x}");
}
```


# Footer
### Source
- 



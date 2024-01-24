---
title: Rust Closure
creation date: 2022-12-10 21:45
aliases: []
tags: reading rust filed
---

# Rust Closure
Anonymous functions created using the |..| syntax. 

>[!note] "Closes over its enviroment"

Closures infer their argruments and return types that has access to the variables in the scope that it's defined.

> [!warning] The closure borrows any variables it uses.

```Rust
let add_one = |x: i32| -> i32 {1 + x};
fn add_one(x: i32) -> {1 + x}
```
Closures do not need to be type annotated but it adds extra explicitness.


## Moving Closures
A second type of closure is called a **moving closure** which are indicated using the **move** keyword. 

The difference between an ordinary closure and a moving closure is that ordinary closures create a reference while moving closures take ownership of all variables.

## Accepting Closures as Arguments
Closures are most useful as an argument to another function.
```Rust
fn twice<F: Fn(i32) -> i32(x:i32, f: F) -> i32 {
	f(x) + f(x)
}

fn main() {
	let square = |x:i32| {x + x};
	twice(5, square);
}
```

# Footer
### Source
- 



---
title: Ownership
creation date: 2022-11-23 00:59
aliases: [rust ownership]
tags: reading rust filed
---

# Ownership
- Ownership is how a Rust program manages memory. 
- Unlike other languages that specify allocation of memory implicity or use automatic garbase collection. Rust magaes memory through a system of ownership.
- There are three rules:
	1. Each value has an owner
	2. Only one owner
	3. Value gets dropped if its owner goes out of scope

In order to support a mutable, growable piece of data, we need to allocate an amount of memory on the heap, unknown at compile time, to hold the contents. This means:
- The memory must be request from the memory allocator at runtime.
- We need a way of return this memory to the allocator when we're done with our string

When a variable goes out of scope. Rust automatically calls the **drop** function and cleans up the heap memory for that variable.

### Ways variables and Data Interact: Clone
If we want to deeply copy the head data, we can use the **clone** method.
> [!note] This is primarily appled to [[Rust Strings|strings]]. Integers have a known size at compile time.

### Ownership and Functions
Pasing a variable to a function will more or copy, just as assignment does.
```Rust
fn main() {
    let s = String::from("hello");  // s comes into scope

    takes_ownership(s);             // s's value moves into the function...
                                    // ... and so is no longer valid here

    let x = 5;                      // x comes into scope

    makes_copy(x);                  // x would move into the function,
                                    // but i32 is Copy, so it's okay to still
                                    // use x afterward

} // Here, x goes out of scope, then s. But because s's value was moved, nothing
  // special happens.

fn takes_ownership(some_string: String) { // some_string comes into scope
    println!("{}", some_string);
} // Here, some_string goes out of scope and `drop` is called. The backing
  // memory is freed.

fn makes_copy(some_integer: i32) { // some_integer comes into scope
    println!("{}", some_integer);
} // Here, some_integer goes out of scope. Nothing special happens.

```




[[The Stack and the Heap]]

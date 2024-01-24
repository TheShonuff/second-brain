---
title: References & Borrowing
creation date: 2022-11-23 01:05
aliases: []
tags: reading rust filed
---

# References & Borrowing
A reference is like a pointer in that it's an address we can follow to access the data stored at that address; That data is owned by some other variable.

References default to immutable even if the reference is mutable 

- The **&** symbol is a reference. They allow you to refer to some value without taking [[Ownership]]of it.
- The opposite of referencing a value is dereferencing with the * operator.

```Rust
fn main() {
    let s1 = String::from("hello");

    let len = calculate_length(&s1);

    println!("The length of '{}' is {}.", s1, len);
}

fn calculate_length(s: &String) -> usize {
    s.len()
}
```

![[Pasted image 20221204234718.png|650]]

## Mutable References
If you have a mutable reference to a value, you can have no other references to that value. 
```Rust 
fn main() { 
	let mut s = String::from("hello"); 
	change(&mut s); 
} 

fn change(some_string: &mut String) { 
	some_string.push_str(", world"); 
}
```
We can use curly braces to change the scope to allow for multiple references. 
```Rust 
fn main() { 
	let mut s = String::from("hello"); 
	change(&mut s); 
} 
fn change(some_string: &mut String) { 
some_string.push_str(", world"); 
}
```

Mutable reference have a restriction. You can only have one mutable reference to a particular piece of data in a particular scope. The following code will fail
```rust
let mut s = String::from("hello");

let r1 = $mut s;
let r2 = $mut s;
```

The benefit of this restriction is that it prevents data races which is similiar to a race condition. This occurs when
1. Two or more pointers access the same data at the same time.
2. At least one of the pointers is being used to write to the data.
3. There's no mechanism being used to synchronize access to the data. 




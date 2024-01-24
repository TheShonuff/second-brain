---
title: Strcuts
creation date: 2022-11-26 00:54
aliases: [Rust Structures]
tags: reading rust filed
---

# Structs
Are the rust version of "object-oriented" "Classes" 

Methods are defined in the implemenation block 

Structs are similiar to tuples, defined in [[Compound Types]], that they can hold multiple related values of different types. However unlike tuples every piece of data needs to be named.

```rust 
struct user {
	active: bool,
	username: String,
	email: String,
	sign_in_count: u64,
}
```

> [!note] it's good practice to have the final data have a trailing comma 

To use a struct after it's be defined, and instance is created of that struct by specifying concrete values for each of the fields. 

```rust
fn main() {
	let user1 = User {
	email: String::from("someone@example.com"),
	username: String::from("someusername123"),
	active: true,
	sign_in_count: 1, 
	}
}
```

Like object-oriented programming we use dot notation to get a specific value.

```rust 
user1.email = String::("anotheremail@example.com")
```

We can build a function that works with structs 
```rust 
fn build_user(email: String, username: String) -> User {
	user {
		email: email,
		username: username,
		active: true,
		sign_in_count: 1,
	}
}
```

# Tuple Structs
Rust also supports structures that look similar to tuples. Tuple structs have added meaning the struct name provides but don't have names associated with their fields. They only have types of fields.
```Rust
struct color(i32,i32,i32);
fn main() {
	let black = Color(0,0,0);
}
```


## Instantiating with struct::new( ) 
In order to insitate a new structure with the ::new() the function has to be defined. This is a type of [[Rust Associated Functions]]

```Rust
struct Block {
	width: u32,
	height: u32,
	height: u32,
}

impl Block {
	fn new(arr: &[u32]) -> Block {
		Block {
			width: arr[0],
			length: arr[1],
			height: arr[2],
		}
	}
}
```
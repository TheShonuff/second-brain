---
title: Rust Strings
creation date: 2022-12-04 23:16
aliases: []
tags: reading Rust filed
---

# Rust Strings
Unlike the other rust [[Data Types]] that are all a know size and can be stored on the stack. Strings are more complex and stored on the [[The Stack and the Heap|Heap]].  

We can create String from a *string literal* using the **from** keyword. 

>[!note] String literal types are **$'static str**
>

```Rust
let s = String::from("Hello");
```

> [!note] String literals are immutable. They're hardcoded directly into the final executable

A mutable string can be created with the following.
```Rust
let mut s = String::from("hello");
s.push_str(", world");
```

A String is made up of three parts
1. A pointer to the memory that holds the contents 
2. A length
3. A Capacity

![[Pasted image 20221204233304.png]]
>[!note] **&str** is a string slice

Rust has more than only **&str**. A **String** is a heap-allocated string. This string is growable and is also guranteed to be UTF-8. **String** are commonly created by converting from a string slice using the *to_string* method.
```Rust
let mut s = "Hello".to_string();
s.push_str(", world.");
```

**String** will coerce into **&str** with an &:

```Rust
fn takes_slice(slice: &str) {
	println!("Got:{}", slice);
}

fn main() {
	let s = "Hello".to_string();
	takes_slice(&s);
}
```

> [!warning] Because strings are valid UTF-8, they do **not** support indexing.

## Slicing
You can get a slice of a string with the slicing syntax.
```Rust
let dog = "hackiko";
let hachi = &dog[0..5];
```

If we're breaking up a string we don't need to specify some values. Here's an example of captializing the first letter and lower case everything else
```Rust
let name = "joHn";
let first = &name[..1];
let rest = $nasme[1..];
let result = format!("{}{}", first.to_uppercase(), rest.tolowercase())
```

We can get the middle of a slice
```Rust
let dog = "hackiko";
let mid = dog.len() / 2 ;
let result = &dog[mid -1 .. mid];
```

## Concatenation
If you have a **String** you can concatenate a **&str** to the end.
```Rust
let hello = "Hello ".to_string();
let world = "world!";
let hello_world = hello + world;
```
But if you have two **String** you need an **&**
```Rust
let hello = "Hello ".to_string();
let world = "world!".to_string();
let hello_world = hello + &world;
```

## Iterating 
```Rust
for c in my_string.chars() {
	//do something
}
```
To have the index 
```Rust 
for (index, character) in my_string.chars().enumerate(){
	//do something
}
```

## to_owned( ) vs to_string( )
Using *to_owned( )* seems to be the preferred method to converting a string literal to a string.

> [!tip] String is owned and &str is not owned


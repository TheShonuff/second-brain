---
title: Standard Library Collections
creation date: 2022-11-27 23:15
aliases: []
tags: reading rust
---

# Standard Library Collections

## Vector
Vectors allow you to sore more than one value in a single data structure that puts all the values next to each other in memory.
**Vec\<T>**

> [!note] Think vector as an array like in other languages. We can push and pop items in and out of the vector. 

The vector provided by the standard library can hold **any type**.

To create an empty vector use

```rust 
let v: Vec<i32> = Vec::new()
```

using vec! macro, this will create a new vector that holds the values supplied. 

```rust 
let v = vec![1,2,3];
```

### Updating a Vector
To create a vector and add elements to it we can use push.

```rust
let mut v = Vec::nec();
v.push(5);
v.push(6);
v.push(7);
v.push(8);
```
With this mutable vector we can add elements to it. *Rust infers that the data type is i32.*

### Reading Elements of Vectors
There are two ways to get values from a vector. Indexing or using the get method. 
```rust
let v = vec![1,2,3,4,5];

let third: &i32 = &v[2];
println!("The third element is {}}", third)

or 

let third: Option<&i32> = v.get(2);
match third {
	Some(third) => println!("The third element is {}", third)
	none => println!("There is no third element")
}
```




## HashMap
similiar to a dictionary in other languages. We can use key, values pairs to return values. 


# Footer
### Source
- 



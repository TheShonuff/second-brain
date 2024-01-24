---
title: Vectors
creation date: 2022-11-30 23:27
aliases: []
tags: reading rust filed
---

# Vectors
Vectors are a *collection* type. Their similiar to how array's are in Javascript where they're mutable and we can push and pop elements from the collection.

Vectors store all values next to each other in memory.

To create an empty vector

```rust
let v; Vec<i32> = Vec::new();
```

Vectors are implemented using [[generics]] 

It's more common to create a vector that already holds values

```rust
let v = vec![1,2,3];
```


## Updating a Vector
```rust
let mut v = Vec::new();

v.push(5);
v.push(6);
```

## Reading Elements of Vectors
```rust
let v = vec![1,2,3,4,5];

let third: &i32 = &v[2];
let third: Option<&i32> = v.get(2);
```

## Iterating Over the Values
```rust
let v = vec![100,32,57];
for i in &v {
	println!("{}", i);
}
```
A mutable reference example
```rust
let mut v = vec![100,32,57];
for i in &mut v {
	*i += 50;
}
```
To change the value the mutable vector reference we have to use the deference operator * to get the value in i before using the += operator.



# Footer
### Source
- 



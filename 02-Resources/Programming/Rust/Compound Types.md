---
title: Compound Types
creation date: 2022-11-20 22:19
aliases: [rust compound types]
tags: reading rust filed
---

# Compound Types
*Can group multipe values into one type.*

There are several two primitive compouind types in rust
1. Tuple
	1. **Store multiple values of any type**
	2. Can use dot syntax to access items in a tuple.
	3. Tuples maximum is 12
2. Array's
	1. **Every value must be the same type**
	2. can be specifed by comma delimited
	3. limited to a size of 32 items in an array
	4. Can be called with a fixed size and type

## Array's
Array's are useful when you want the data allocated on the stack rather than the heap.

Array's are typically used when the data **doesn't** change. If the array is anticapted to cahnge use a [[vector]] instead.

An arry in rust is a *fixed-sized collection of elements* denoted by [T; N] where **T** is the element type and **N** is the compile-time constant size of the array. 

>[!note] An Array has to be a collection of the same type

When initalizing an array you can use array = values. Another syntax when initializing from another array a colon is used

```rust 
let variable_name:[dataType; array_size] = [value1, value2, value3]
```

> [!note] Array's are accessed with square brackets

```rust
let a: [i32; 5] = [1,2,3,4,5];
lef first = a[0];
```

---
## Tuples
A general way of group together a number of values with a variety of types. *Tuples have a fixed length, when declared, they cannot change*.

```rust
let tup: (i32, f64, u8) = (500, 6.4, 1);
```

>[!note] Tuples are accessed using dot notation. 

```rust
let x:(i32, f64, u8) = (500, 6.4, 1);
let five_hundred = x.0
```
A tuple without any values has a speical name: **unit**.

# Footer
### Source
- 



---
title: Rust Map Function
creation date: 2022-12-12 23:39
aliases: []
tags: rust iterator/adapter
---

# Rust Map 
Map is comonly used as a tool for dealing with lists and collections. It's an **essential** method for working with with [[Rust Iterators|Iterators]].

The **map** method offers a way to apply a function or a [[Rust Closure|closure]] on each element from a list.

>[!tip] A key to functional programming methodology which offers a way to transform a collection of type A to a collection of elements of type B.

```Rust
let numbers = vec![3,6,9,12];
let result: Vec<i32> = numbers
	.iter()
	.map(|n| n * 10)
	.collect();
```

## Map returns an iterator
The reutrn type of **.map( )** is also an iterator. We can chain multiple transformations togther.

```Rust
let numbers = vec![3,6,9,12];
let result: Vec<i32> = numbers
	.iter()
	.map(|n| n * 10)
	.map(|n| n / 3)
	.collect();
```

We can return a [[Vectors|vector]] of results by using the **.collect( )** method. *it acts as a consumer to the iterator, acquiring all elements and storing them into a vector.*

# Examples
```Rust
let pairs = vec![(0,1),(2,3),(4,5)];
pairs
	.into_iter()
	.map(|(x,y)| (x+1,y))
	.for_each(|t| prinln!("{:?}", t))
```




# Sources
[Good Article](https://www.newline.co/@kkostov/the-rust-map-function-a-gateway-to-iterators--f991b22b)

---
title: Rust Iterators
creation date: 2022-12-12 23:41
aliases: []
tags: rust filed
---

# Rust Iterators
- Data structures that contain a sequence of objects that allow iteration. 
- Rust iterators are lazily evaluated.
	- no calculation is performed until the result is requested.


## .iter( ) -

> [!tip] Yields &T - immutable references

The most common method of the three. Allows iteration of each value as an **immutable reference** 

## .into_inter( ) -

> [!tip] Yields any of T(moved value), &T or &mut T

A method that comes from the **IntoIterator** [[Traits|trait]]. This is useful when the type respresents some sort of collection of data and most notably allows for an iteration over object of the type in a **for** loop.

## .inter_mut( ) - 

> [!tip] Yields &mut T mutable references

The least used method. Allows the iteration of each element as a **mutable reference**.

## Consuming Adapters
The **iterator** [[Traits|trait]] has a number of different methods with defualt implementations provided by the standard library. Methods that call the **next** method are considered **consuming adaptors**.

>[!note] The **next** method changes the internal state of the iterator uses to keep track of where it is in the sequence.

The **sum** method is an another example. It takes ownership of the iterator and iterates through the items repeatedly calling the **next** method.

### Consuming Adaptors
- find
- fold
- sum


## Methods that Produce Other Iterators
Iterator adaptors are methods defined on the **Iterator** [[Traits|trait]] that do not consume the iterator. Instead they produce different iterators by changing some aspect of the original iterator.

### Iterator Adaptors
- [[Rust Map|Map]]
- [[Rust Filter|Filter]]
- [[Rust Position Iterator|Position]]

>[!note] [Rust-lang.org](https://doc.rust-lang.org/stable/std/iter/index.html#adapters) has a lot more about Adapters

Then next method used after an Iterator adaptor is the **collect** method. 

```Rust
let mut numbers = vec![1,2,3,4];
for x in $mut numbers {
	*x *= 3;
}
prinln!("{?}". numbers);
```


# Sources
[BecomeBetterProgrammer.com](https://www.becomebetterprogrammer.com/rust-iter-vs-iter_mut-vs-into_iter/)
[Book-Rust-Lang.org](https://doc.rust-lang.org/book/ch13-02-iterators.html)
[Doc.Rust-Lang.org](https://doc.rust-lang.org/stable/std/iter/#iterator)
[Implementing Iterator](https://doc.rust-lang.org/stable/std/iter/index.html#implementing-iterator)


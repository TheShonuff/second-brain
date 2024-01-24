---
title: Rust Position Iterator
creation date: 2022-12-14 00:04
aliases: []
tags: rust iterator
---

# Rust Position Iterator
The **.position( )** takes a closure that returns true or false. It applies this closure to each element of the iterator and if one of them returns true, then **position( )** returns *Some(index)*. If all of them return false, it returns *None*.

> [!tip] **.position( )** is short circuiting. It will stop processing as soon as it finds a true.





# Sources
[Rust Docs](https://doc.rust-lang.org/std/iter/trait.Iterator.html#method.position)
---
title: Idiomatic Rust
creation date: 2022-12-11 19:46
aliases: []
tags: rust
---

# Idiomatic Rust

Rust Format - **rustfmt**: code formatter
*alternatively* we can call **cargo fmt** -> formats all the code in a crate.

cargo clippy - *linter* compiles code and checks for problems. 
- style
- correctness
- complexity


## Attributes
fall into #\[\] 
allow one or more parameters.
Put outside the function

## Documentation
```sh
cargo doc --no-deps --open
```

Documentation comments are three ///
as opposed to a regular comment //

We can also use block comments /\*\* \*\*/

### inner documentation
//! or /\*! !\*/

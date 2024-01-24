---
title: Rust Fundamentals
creation date: 2022-11-20 20:48
aliases: []
tags: rust filed
---

# Cargo
Is the base of Rust. it's a:
1. package manager
2. test runner
3. compiler
4. docs generator

To start a new package with Cargo use 
```bash
cargo new <file name>
```

Cargo defaults to **--bin** to make a binary program. To make a library pass **--lib** instead

Equvilant to the package.json rust create a *Cargo.toml* that contains all the project information. This is called a **manifest**

What's interesting is we can use **cargo run** within the *src* directory to compile and run the binary.

# Footer
### Source

[cargo guide](https://doc.rust-lang.org/stable/cargo/guide/index.html)



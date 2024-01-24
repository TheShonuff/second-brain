---
tags:
  - rust
---
# Rust Associated Functions
All functions defined with an [[Rust Implementation|impl]] block are called **associated functions**. This is because they are **associated** with the type named after the [[Rust Implementation|impl]]. Functions that don not use *self* as their first parameter are not methods and do not need an instance of the type to work with.

> [!note] Associated Functions that are not methods are often used for constructors that will return a new instance of the struct.




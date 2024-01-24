---
title: Rust - Option
creation date: 2022-12-07 10:54
aliases: []
tags: Rust Filed
---

# Option Type

Another enum defined by the standard library. The **option** type encode the very common scenario in which a value could be something or it could be nothing.

>[!note] Rust does not have *null*. It's an **option**

[Rust Documentation - Option](https://doc.rust-lang.org/std/option/enum.Option.html)

Every instance is either
- None
- Some(*value*).

If you're sure an **option** has a real value inside, the *expect()* and *unwrap()* are used. If the variable is None, the program will exit.

The most basic way to see whether an **Option** has a value or not is to use the pattern matching with a [[Match]] expression.

## unwrap 
If for when you demand there to be a value to continue running the program. 

When called on a result, **unwrap** will return the value and will panic when there isn't one. Likewise with **Options** if it has some value, it will return that value, but if the value is None it will panic.

## expect
Works similarly to **unwrap** but with the addition of custom panic message. If you're wanting a more friendly error message from *Err* or *None* you can use **expect**.
```Rust
let status = get_status("joe").expect("satatus fetching");
```

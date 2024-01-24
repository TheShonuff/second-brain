---
title: Functions1
creation date: 2022-11-20 21:44
aliases: [rust functions]
tags: reading rust filed
---

# Rust Functions
Functions are declared using the **fn** or the "fun" with snake casing.

Functions can appear anywhere in the file. They don't have to be declared before they're called.

You **must** specify the return with the arrow **->** after the function statement but before the braces. 

```rust
fn do_stuff(qty: f64, oz: f64) -> f64 {
	println!("{} {} - oz sarsaparillas(s)!", qty, oz);
	qty * oz
}
```


## Parameters
Are special variables that are part of a function's signature. When a function has parameteres, you can provide it with concrete values for those parameters.

>[!note] These a re technically called **arguments**

A type must declared for each type of parameter. When defining multiple parameter declarations use commas.

## Statements and Expressions
Function bodies are made up of a series of statements optionally ending in an expression. 

>[!note] Rust is an expression-based language

- **Statements** are instructions that perfom some action and do not return a value.
	- let y = 6;
- **Expressions** evaluate to a resulting value.
	- 5 + 6
	- Calling a function is an expression
	- calling a macro is an expression

## Return Values 
Return values are not named but a type must be declared. We can return early from a function block with a **return** keyword. 


# Footer
### Source
- 



---
title: Control Flow
creation date: 2022-11-23 00:11
aliases: [rust control flow]
tags: reading rust filed
---

# Control Flow
Like all major programming languages Rust has the **if expression**. Where a condition is provided and if the condition is met will run a block of code. 

```rust 
fn main() {
	let number = 3;
	if number < 5 {
		println!("Condition was true");
	} else {
		println!("Condition was false");
	}
}
```

>[!note] You don''t need semicolons on the "return" expression as they'll be treated as tail expressions

We can optionally provide an *else* expression to perform and action if the initally condition is not met. If we don't provide an *else* epxression the block of code is skipped. 

## Handling multiple conditions 
In rust we use *else if* to handle multiple conditions. There is a space in the *else if*

## Using *if* in a let statement 
Because **if** is an expression we can use it on the right side of a **let** statement to assign the outcome to a variable. 

```rust
fn main()
	let condition = true;
	let number = if condition { 5 } else { 6 };
	println!("The value of number is: {number}");
```

## Repetition with Loops 
There are three kinds of loops in rust: **loop, while, for**

## Loop 
The loop keyword tells Rust to execute a block of code over and over again forever or until you explicitl tell it to stop. The **break** keyword within the loop tells the program to stop executing the loop.

### Returning values from loops
To return a value from a loop include the variable or expression after the **break** keyword.
```Rust
fn main(){
	let mut counter = 0;
	let result = loop {
		counter += 1;
		if counter == 10 {
			break counter * 2;
		}
	};
	println!("The result is {result}");
}
```

### Loop Labels to Disambiguate Between Multiple Loops
If you have loops within loops, **break** and **continue** apply to the innermost loop. We can optionally supply a loop label that can be used with **break** and **continue**
```Rust
fn main() {
	let mut count = 0;
	'counting_up: loop {
		println!("count = {count}");
		let mut remaining = 10;
		loop {
			println!("Remaining = {remaining}");
			if remaining == 0 {
				break;
			}
			if count == 2{
				break 'counting_up;
			}
			remaining -= 1;
		}
		count += 1;
	}
	println!("End count = {count}");
}
```

## While Loop
A program will often need to evaluate a condition within a loop. While the condition is true, the loop runs. When the condition ceases to be true, the program calls **break**.
```Rust
fn main(){
	let mut number = 3;
	while number != 0 {
		println!("{number}");
		number -= 1;
	}
	println!("LIFTOFF!!!");
}
```


## For Loop
```Rust
fn main(){
	for number in (1..4).rev(){
		println!("{number}");
	}
	println!("LIFTOFF!");
}
```

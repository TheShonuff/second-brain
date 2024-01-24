---
title: Enums
creation date: 2022-11-27 23:19
aliases: []
tags: reading rust filed
---

# Enums
Enumerations aka enums. They allow you to define a type be enumerating its possible variants. 

Algebraic data types.

```rust
enum IpAddr {
	V4(u8, u8, u8, u8),
	V6(String),
}
```

>[!note] *V4* and *V6* are **variants**

## Enum Values
we can create instances of each of the two variants in IpAddrKind
```Rust
let home = IpAddr::V4(127, 0 , 0, 1);
let loopback = IpAddr::V6(String::from("::1"));
```

An advantge over [[Structs]] is that we can define 1 enum as opposed to several structs.
```Rust
enum Message {
	Quit,
	Move{x:i32,y:i32},
	Write(String),
	ChangeColor(i32,i32,i32)
}
```
The Struct version would be...
```Rust
struct QuiteMessage;
struct MoveMessage {
	x: i32,
	y: i32,
}
struct WriteMessage(String);
struct ChangeColorMessage(i32,i32,i32);
```

A Smiliarity between enums and structs is that we able to define methods on enums.
```Rust 
impl Message{
	fn call(&self){
		// Method Body
	}
}

let m = Message::Write(String::from("Hello"));
m.call();
```







# Footer
### Source
- 



---
title: Rust Methods
creation date: 2022-12-06 00:35
aliases: []
tags: reading rust filed
---

# Rust Methods
Methods are similar to [[Rust Functions|functions]] in that we can declare them with the **fn** keyword, they can have parameters and return a value. They're defined within the context of [[Structs]] or [[Enums|enum]].
>[!note] The first paramter is **always** self

```Rust
struct Rectangle {
	width: u32,
	height: u32,
}
impl Rectangle {
	fn area(&self) -> u32 {
		self.width * self.height
	}
}

fn main() {
	let rect1 = Rectangle {
		width: 30,
		height: 50,
	};
	println!("The area is {} square pixels", rect1.area())
}
```

- All functions defined with an impl block are called [[Rust Associated Functions|Associated Functions]]
	- They're *associated* with the type named after impl.
	- The **self** keyword in the return type and in the body are aliases for the type.
```Rust
impl Rectangle {
	fn square(Size: u32) -> Self {
		Self {
			width: size,
			height: size,
		}
	}
}
```

> [!note] To call this assocaied function: let sq = Rectangle::square(3);



# Footer
### Source
- 



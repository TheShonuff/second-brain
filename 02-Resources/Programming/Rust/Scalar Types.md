---
title: Scalar Types
creation date: 2022-11-20 22:08
aliases: [rust scalar types]
tags: reading rust filed
---

# Scalar Types
- Represents a single value.
- There are 4 scalar types in rust
	- Integer
	- Floats
	- Boolean
	- Character
	

> [!note] When a number needs a sign (+/-), it's signed. If it's assumed positive then it's unsigned.

## Floats
1. f32 and f64 are standard
	- **The default type is f64**
	- All floating point numbers are [[signed integer|signed]]
	- Floating Point Literals
		1. follow IEEE-754 standard
		2. needs at leats one digit before the decimal

## Boolean
1. specifed as **bool**
		1. true
		2. false
2. Are 1 bye in size.

## Character
Rust's **char** type is the most primitive alphabetic type.
1. specifed as **char**
	- always 4 bytes
	- specified with *single quotes*



The difference between [[signed integer]] and [[unsigned integer]] is that the unsigned integar is positive, non negative, values.

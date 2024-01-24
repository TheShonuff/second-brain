---
title: PHP Conditionals
Created: 2024-01-04 21:14
tags:
  - php
aliases:
---
# PHP Conditionals
- **TRUE** or **FALSE** are written in all capitals
- Identical and Not identical operators
	- `===` 3 equals is the identical tester 
	- `!==` is the not identical tester
- Use `elseif` to chain multiple statements.

>[!note] `==` is a comparison operator which compares the value of the variables. But `===` compares the value and the data type.
## Ternary
- The first operand is the condition to check followed by a `?`
- The second operand is an expression to `return` if the condition is **TRUE**
- the third operand is an expression to `return` if the condition is **FALSE**
```php
$isClicked = FALSE;
$link_color = $isClicked ? "purple" : "blue";
```


## Nested Conditionals
- `||` - The **or** condition returns **TRUE** if either or both values are **TRUE**
	- can use `or` but has lower precedence
- `&&` - The **and** condition returns **TRUE** if both values are **TRUE**
	- can use `and` but has lower precedenc
- `!` - The **not** operator returns the reverse
- `XOR` - exclusive or. Evalutes to **TRUE** if only the right operand or left operance is **TRUE** but *not both.*

## Common Mistakes with Conditionals
- Not treating expressions as distinct


## If Statements
- There are two types of syntax for handling these conditions. One uses curly brackets and the other uses a color.

```PHP
if ($condition < $num){
	echo $num
}
```

```PHP
if ($condition < $num):
	echo $num
endif;
```

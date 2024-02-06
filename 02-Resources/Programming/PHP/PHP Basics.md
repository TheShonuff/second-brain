---
id: PHP Basics
aliases:
  - PHP Basics
tags:
  - php
Created: 2023-12-29 21:57
title: PHP Basics
---
# PHP Basics
- Embedding php in html uses `<?php` and `?>`
- Every statement ends with `;`
- a file with a `.php` extension the `?>` is implied and not needed
- Comments
	- Single line use `#` or `//`
	- multi line use `/*` `*/`
- 

## Strings
- Strings are uses with double quotes
- String can be concatenated using the `.` operator
- To check string length use `strlen($string)`
    - This will convert the value to a int to be compared in condition testing.
```Php
echo "one" . "two";
```


## Variables
- Declaring a variable we uses the `$name` format.
	- Also known as the *sigil
>[!tip] snake case is the convention for naming variables
- The variables are used with the *sigil* in the front.
- Variables can be used in a string without special brakets. The *sigil* indicates that it's a variable.

```Php
echo "I have a $color dog named $dog_name and her favorite food is $favorite_food"
```

- However we can still wrap the variable in curly braces to avoid confusion

```php
echo "I have a ${color} dog named ${dog_name} and her favorite food is ${favorite_food}"
```

## Concatentating Assignment
- Performed using `.=`
	- similar to `+=` in Javascript or Python

## Reference Assignment
- Using the `=&` the variable on the left should point or refer, to the exact same data as the variable on the right.
	- Changes made to one variable will affect the other.

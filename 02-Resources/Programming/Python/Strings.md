---
tags:
  - python
---
# Strings
- A **string** sequence of characters
- A **string literal** is a string value specified in the source code of a program.
- Can be enclosed in single or double quotes
- The string type is a special construct known as **sequence type**
	- A type that specifies a collection of objects ordered from left to right.
- Strings are **immutable**

## Operations on Strings
- Concatenation `'ab' + 'cd'`
- successive concatenation `3 * 'jon'`
- length `len('jon')`
- indexing `'jon'[1]`
- slicing `'jon'[1:2]`
- strip `str.strip()` Removes leading and trailing whitespace.

## String Formatting
- Formatted string literals are called **f-strings**
- Evaluated as the program executes.
- Start with an **f** character.
	- `print(f'{number} burritos cost ${amount})`
- An **=** sign is provided after the expression both the expression and result will print
	- `print(f'{2**2})` = `2**2=4`

| Type  | Description                              | Example                 | Output      |
| ----- | ---------------------------------------- | ----------------------- | ----------- |
| s     | String(default presentation type)        | `print(f'{name:s}')`    | Aiden       |
| d     | decimal(integer values only)             | `print(f'{number:d}'`   | 4           |
| b     | Binary                                   | `print(f'{number:b}'`   | 1001        |
| x,X   | Hexadecimal                              | `print(f'{number:x}'`   | 1f          |
| e     | Exponent notation                        | `print(f'{number:e}'`   | 4.40000e+01 |
| f     | Fixed-point notation                     | `print(f'{number:f}'`   | 4.000000    |
| .numf | Fixed-point notation (programmer define) | `print(f'{number:.2f}'` | 4.00        |
| 0numd | Leading 0 notation                       | `print(f'{number:03d}'` | 004         |

## Advanced Formatting
- Can achieve complicated graph layouts
- A **field width** defines the minimum number of characters that must be instered into the string. If the replacement is smaller in size then the string is padded with space characters.
- **Integers** will be right aligned
- **Strings** will be left aligned
- A format specification can include an **alignment character**
	- `<` left aligned
	- `>` right aligned
	- `^` center aligned
- A **fill character** is used to pad a replacement field.
	- The default fill is an empty space
	- Is specified by placing to the left of the **alignment character**
- **Floating point precision** can be supplied with `.xf` where `x` is the number of decimals.
	- Follows the **field width** component
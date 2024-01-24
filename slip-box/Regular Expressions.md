---
title: Regular Expressions
Created: 2024-01-16 20:41
tags:
  - regex
aliases:
  - regex
---
# Regular Expressions
- A special sequence of characters that describe a pattern of text that should be found, or matched, in a string or document. 

## Literals
- The simplest text that can match with regular expressions are **literals**.
	- The regular expression contains the exact text that needs to be matched.
## Alternation
- Using the `|` symbol, match the characters preceding the `|` or the characters after the `|`.
	- `baboons|gorillas` will match `baboons` in the text `I love babooks` but it will also match `gorillas` in the text `I love gorillas`.
## Character Sets
- denoted by a pair of brackets `[]`, let the user match one characyer from a series of characters, allowing for matches with incorrect or different spelling.
	- `con[sc]en[sc]us` will match `consensus`, the correct spelling, but also match `concensus`, `consencus`, and `concencus`.
- Using the `^` in the front of the character set *negates* the set.
	- These are called *negated sets*
	- `[^cat]` matches any character **not** `c`, `a`, `t`.
## Wilcards
- `.` Will match any single character.
	- `.........` will match `orangutan` or `marsupial`
	- `I at . bananas` will match `I ate 3 bananas`
>[!tip] To match a actual period use the `\` escape before the period

## Ranges
- Specify a range of characters to match.
- `[abc]` is equivilant to `[a-c]`
- Multiple ranges can be specified 
	- `[A-Za-z]` to match a single capitial or lowercase alphabetical character.
>[!warning] anything within `[]` matches a single character.

## Shorthand Character Classes
- Represent common ranges
- `\w` - The "word character" represents the regex range `[A-Za-z0-9_]` matching a single uppercase, lowercase, digit or underscore
- `\d` - The "digit character" represents the regex range `[0-9]` 
- `\s` - The "whitespace character" represents the regex range `[\t\r\n\f\v]`, matching a single space, tab, carriage return, line break, form feed, or vertical tab.
## Grouping
- Denoted with `()`, allows for grouping parts of regular expressions.
- `I love (baboons|gorillas)` will match `I love` and then match `baboons` or `gorillas`.
## Quantifiers - Fixed
- Denoted with `{}` let us indicate the exact quantity of a character we wish to match.
- `\w{3}` - Will match exactly 3 word characters
- `\w{4,7}` - Will match a minimum 4 word characters and at maximum 7 word characters
>[!warning] Quantifiers are greedy, They will match the greatest quantity of characters they possibly can.
>`mo{2,4}` will match `moooo` but not `moo` or `mooo`
## Quantifiers - Optional
- Indicated by the `?`. Allows to indicate a character in a regex is optional, or can appear zero or one times.
	- Only applies to the character directly *before* the `?`
- `humou?r` matches `humo`

## Quantifiers - 0 or More, 1 or More
- The *Kleene star*, denoted with `*` matches the preceding character zero or more times.
	- `meo*w` will match the characters `me` followed by zero or more `o`, followed by a `w`.
		- Will match `mew`, `meow`, `meooow`, and `meooooooow`.
- The *Kleene plus* denoted by the `+` matches the preceding character one or more times.
	- `meo+w` will match the characters `me`, followed by one ore more `o`'s, followed by a `w`.
		- Will match `meow`, `meoow`, and `meooooooow` but not `mew`.

## Anchors
- The `^` and `$` are used to match text at the start and the end of a string, respectively.
	- `^Monkeys: my mortal enemy$` The `^` ensures that the matched text begins with `Monkeys`, and the `$` ensures the match text ends at enemy.
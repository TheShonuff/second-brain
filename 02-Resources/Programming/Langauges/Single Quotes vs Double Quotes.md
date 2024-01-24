---
title: Single Quotes vs Double Quotes 
creation date: 2022-11-20 14:15
aliases: []
tags: shell filed
---

# Single Quotes vs Double Quotes
Often times the single and double quotes are interchange. Some *styles* seem to prefer using single quotes. There is some minor differences in shell scripting that you need to be aware of. 

Single quotes *will **not** [[interpolate]]* anything. Enclosing character with the single quote preserves the literal value of each character within the quotes.
>[!note] A signle quote may not occure between signle quotes, even whe preceded by a backslash

Double quotes *will [[interpolate]].* Enclosing characters in double quotes preserves the literal value of characters with the exception of $ and backslash. 

A table illustrating some examples.
a = apple
arr = (apple)

| Expression  | Result    | Comments                                    |
| ----------- | --------- | ------------------------------------------- |
| "$a"        | apple     | variables are expanded inside ""            |
| '$a'        | $a        | variables are not expanded inside ''        |
| "'$a'"      | 'apple'   | '' has no special meaning inside ""         |
| '"$a"'      | " $a"     | "" treated litteraly inside ''              |
| '${arr[0]}' | ${arr[0]} | array access not possible inside ''         |
| "${arr[0]}" | apple     | array access works inside ""                |
| '!cmd'      | !cmd      | history expansion character ! is ignored    |
| "!cmd"      | cmd args  | expands to the most recent command matching |



# Footer
### Source
- 

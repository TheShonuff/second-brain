---
title: metacharachters
creation date: 2022-11-09 23:39
tags:
  - python/regex
  - python
---

# metacharacters
> [!note]    . ^ $ * + ? { } [ ] \ | ( ) 

The \[ and **\]** are used to specify a character class, which is a set of characters that wish to be matched.

This will match any character a,b,c.
```python
[abc]
# the same as
[a-c]
```

>[!note] Metacharacters inside square brackets or *character class* is stripped of it's special nature.

**^** can be considered the *not* character. The following example will match any character except 5. Will need to be in front of the character to be *not* included. If it appears at the end the **^** will be included in the character class.
```python
[^5]
```

Special squences beginning with \ represent a predefined set of characters. Like a set of digits or letters. \\**w** would match any alphanumeric character.
```python
[a-zA-Z0-0]
# the same as

\w
```




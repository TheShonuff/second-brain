---
title: Performing Matches
creation date: 2022-11-10 00:17
tags:
  - python/regex
  - python
---

# Performing Matches
An object containing a compiled set of regular expressions can be used with a couple of methods to search a string

**match()** - Determine is the regex matches at the beginning of the string

**search()** - Scan through a string, looking for any locations that matches the regex

**findall()** - Find all substrings where the regex matches and returns as a list

**finditer()** - find all substrings where the regex matches and returns them as an iterator.

```python
import re

p = re.compile('[a-z]+')
print(p.match(string))
```





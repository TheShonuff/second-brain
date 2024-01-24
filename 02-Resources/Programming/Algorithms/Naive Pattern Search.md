---
title: Naive Pattern Search
Created: 2023-11-19 22:15
tags:
  - algorithms
aliases:
---
# Naive Pattern Search
- Pattern searching requires two base components
	- A text to scan 
	- A pattern to search for
- Time complexity is $O(nk)$ -> $O(n^2)$
	- Constant backtracking to the next character is a large reason for the slow performance

```Python
def pattern_search(text, pattern):
	print("Input Text:", text, "Input Pattern:", pattern)
	for index in range(len(text)):
		print('Text Index', index)
		match_count = 0
		for char in range(len(pattern)):
			print('Pattern Index', char)
			if pattern[char] == text[index+char]:
				match_count += 1
			else:
				break
		if match_count == len(pattern):
			print(pattern, "Found at index", index)

text = "HAYHAYNEEDLEHAYHAYHAYNEEDLEHAYHAYHAYHAYNEEDLE"
pattern = "NEEDLE"
pattern_search(text, pattern)
```


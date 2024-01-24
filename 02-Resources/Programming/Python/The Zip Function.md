---
title: The Zip Function
Created: 2023-11-22 20:57
tags:
  - python
aliases:
---
# The Zip Function
- Can quickly combine associated data-sets without needing to rely on multi-dimensional lists.
- `zip()` takes two (or more) lists as inputs and returns an *object* that contains a list of pairs. Each pair contains one element from each of the inputs.
- The convert the object to a list, it needs to be wrapped in the list method.
	- This will convert inner *lists* into [[Tuple|tuples]].

```Python
names = ["Jenny", "Alexus", "Sam", "Grace"]
heights = [61, 70, 67, 64]

names_and_heights = zip(names,heights)
converted_list = list(names_and_hehights)

```



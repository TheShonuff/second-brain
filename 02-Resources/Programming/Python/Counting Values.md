---
title: Counting Values
Created: 2023-12-15 22:00
tags:
  - python
  - pandas
aliases:
---
# Counting Values
- The `value_counts()` method lists and counts all the unique values of a column.

```Python
df['column'].value_counts()
```

- The method has a few different parameters we can modify.
	- `normalize=True` will return the precentages instead of raw numbers
	- `ascending=True` will sort from smallest to largest.
- To count specific values supply the value to look for as a list
```Python
df['column'].value_counts()['what to look for']
```

## Summarizing Data
- The series method `describe()` calculates statistical information about the numbers in a numeric column.
- The method will output *numeric columns*
	- **Count** the number of numbers in the column
	- **Mean** the average of the numbers in the column
	- **std** the standard deviation of the numbers in the column
	- **min** the minimum of the numbers in the column
	- **25%, 50%, 75%**: the percentiles of the numbers in the column
	- **Max** the maximum of the numbers in the column.

- The method will output on *text columns*
	- **count** The number of (non-missing) entries in the column
	- **unique** The number of unqiue entries in the column.
	- **top** The most frequent value
	- **freq** the number of times the top value appears.



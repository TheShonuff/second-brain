---
title: Pandas Calculations
Created: 2023-12-19 21:10
tags:
  - python
  - pandas
aliases:
---
# Pandas Calculations

## Column Calculations
- calculations will be applied to all the rows simultaneously.

```Python
df['column_2'] / 2
```
>[!note] divides all of column two in half

```Python
df['column_3'] =  df['column_2'] / 2
```
>[!note] Saves the division of column 2 to column 3

## Combining Columns
```Python
df['col3'] = df['col2'] - df['col1']
```

>[!warning] Operations with `NaN` produce `NaN`

## Rounding
- The `.round()` method can round an entire column
```Python
df['column'] = df['colum'].round(decimals=2)
```







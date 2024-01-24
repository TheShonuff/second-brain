---
title: Indexes
Created: 2023-12-16 23:20
tags:
  - python
  - pandas
aliases:
---
# DataFrame Row Indexes
- The *index* of a DataFrame refers to the *row index*
- By default DataFrames come with a **RangeIndex** where the first row is labelled `0`
	- This can be confirmed by using `df.index`
	- This indicates that the row labels
		- start at 0
		- increase by 1 for each row
		- end *before* reaching the total number of rows.


## Resetting the Index
- It is possible to restore a standard `RangeIndex` by calling the method `.reset_index()`
- The `.reset_index()` method will reset the indices in the new DataFrame.
	- A new *index* column is created.
	- passing in `drop=True` removes the old index values.

## Sorting Rows
- `sort.values()` method will sort from lowest to highest
	- For text it will sort A to Z
	- Passing False to ascending will sort Z to A
>[!warning] `.sort_values()` will only sort values by a column. To sort rows by the index values use `.sort_index()`
- To preserve the DataFrame use the `by` keyword in `.sort_values()`
	- [Documentation](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sort_values.html)
	- Can accept a string or a list of strings.
>[!warning] Using `df['column'].sort_values()` will return a series with only that column.



## Selecting Rows
- DataFrames are zero-indexed
```Python
dataframe.iloc[2]
```
>[!note] would select the third row in the DataFrame

>[!tip] Selecting a single row produces a Series

## .loc vs .iloc
- `.loc[]` index works by using the *index labels*.
```Python
df.loc[list_of_row_labels, list_of_column_labels]

df.loc[[0,3],['Make']]
```
>[!note] Selects the rows labelled `0` to `3` and only from the column labelled `Make`

- `iloc[]` index works using the *position integer* of the rows and columns, instead of the labels.
```Python
df.iloc[list_of_row_positions, list_of_column_positions]

df.iloc[[0,1],[6]]
```
>[!note] Selects the first two rows and the 6th column.

- Selecting multiple columns and rows using slice index.
```Python
df.iloc[0:25, 2:6]
```
>[!note] Selects the first 25 rows and column indexes 2 to 5

### Selecting Multiple Rows
- Selecting multiple rows uses the slice syntax
```Python
dataframe.iloc[start:end]
```

>[!tip] Selecting multiple rows produces a DataFrame

#### Selecting multiple Rows with loc
- A range of labels can be specificed.

## Selecting Rows with Logic
```Python
dataframe[logic expression]
```

```Python
variable = dataframe[dataframe.column >= dataframe.column]
```

- Multiple expressions can be tied togther using `|` `&
	- **Each expression should be enclosed in parens** `()`
- Multiple rows can be selected using `isin()` method.
	- Pass in a list of values to check.
```Python
variable = dataframe[dataframe.column.isin([value, value, value])]
```

### Selecting Rows with Misisng values
- Often we'll need to find and remove rows with missing values.
```Python
df[df['column name'].isnull()]
```

- We then can use that information to drop rows with the missing values.

## Filtering Rows with Booleans
- A boolean mask tells us which rows have a certain property.
- To filter the row pass the pass to the DataFrame.
```Python
is_2023 = (df['Year'] == 2023)
df[is_2023]
```
>[!note] Will only select rows that are *True*

- The comparison operator can be passed directly as well. 
```Python
df[df['year'] == 2023]
```


## Inverting with Not
- Pandas uses the `~` for non/non.

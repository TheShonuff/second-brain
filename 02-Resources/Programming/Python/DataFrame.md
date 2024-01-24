---
title: DataFrame
Created: 2023-11-25 21:13
tags:
  - python
  - pandas
aliases:
---
# DataFrame
- An object that stores data as rows and columns.
	- Each column has a name.
	- Each row has an index.
- Dictionnary can be passed to `pd.DataFrame()` 
	- Each key is a column name and each value is a list of column values.
	- The columns must be the same length or an error will occur.

```Python
df1 = pd.DataFrame({
		'name':['John Smith', 'Jane Doe', 'Joe Schmo'],
		'address':['123 main st', '456 Maple Ave', '789 Broadway'].
		'age':[34,28,51]
})
```

```Python
df2 = pd.DataFrame([
		['John Doe', '123 Main St', 34],
		['Jane Doe', '456 Maple Ave', 28],
		['Joe Schmo', '789 Broadway', 51]
		],
		columns = ['name', 'address', 'age'])
```

| Name       | Address       | Age |
| ---------- | ------------- | --- |
| John Smith | 123 Main st   | 34  |
| Jane Doe   | 456 Maple Ave | 28  |
| Joe Schmo  | 789 Broadway  | 51  |

## Loading From CSV
- The first row of a CSV contains the heading information.
- To load csv into a DataFrame use `.read_csv()` method
- To save to a csv use `to_csv()` method

## Inspect a DataFrame
- `.head()` will display the first 5 rows.
- `.head(10)` will display the first 10 rows.
- `.info()` will give some statistics

## Selecting Columns
- Using dot notation
	- `dataframe_name.column`
- Key Value similiar to dictionary
	- `dataframe_name['column']`

>[!tip] Selecting a single column produces a Series

### Selecting Multiple Columns
- To select two or more columns from a DataFrame, we list the column names.
```Python
new_df = df[['column 1', 'column 2']]
```

>[!tip] Selecting multiple columns produces a new DataFrame


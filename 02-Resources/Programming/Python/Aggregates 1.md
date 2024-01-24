---
tags:
  - python
  - pandas
---
# Aggregates
- A way of creating a single number that describes a group of numbers.
	- Common aggregate statistics include:
		- mean
		- median
		- standard deviation

## Calculating Column Statistics
- The syntax for calculations is 
```Python
df.column_name.command()
```

| Command | Description                       |
| ------- | --------------------------------- |
| mean    | Average of all values in column   |
| std     | Standard deviation                |
| median  | Median                            |
| max     | Maximum value in column           |
| min     | Minimum value in column           |
| count   | Number of values in column        |
| nunique | Number of unique values in column |
| unique  | List of unique values in column                                  |

### Groupby
```Python
df.groupby('column1').column2.measurement()
```
- **column1** is the column we want to groupby
- **column2** is the column we want to perform a measurement
- **measurement** is the function we want to apply.

>[!tip] Produces a Series object

- It's often that the groupby statement is followed by a `reset_index` to clean up the indexs.This operation will change the series into a DataFrame

- Sometimes the operations are more complicated than the common commands.
- In those cases we can use `apply()` method and use a lambda function.

```Python
df.groupby('column1').column2.apply(lambda x : expression).reset_index()
```

- We can groupby more than one column by passing a list of column names.

```Python
df.groupby(['column_1','column_2']).column3.measurement().reset_index()
```

## Pivot Tables
- Reorganizing a table is called pivoting.
```Python
df.pivot(columns='Column_to_pivot',
		index = 'column_to_be_rows',
		values = 'column_to_be_values')
```

>[!tip] call the DataFrame that had the recent groupby performed


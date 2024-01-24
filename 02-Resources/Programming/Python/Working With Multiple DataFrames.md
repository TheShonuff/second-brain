---
title: Working With Multiple DataFrames
Created: 2023-12-12 20:30
tags:
  - pandas
  - python
aliases:
---

---
# Working With Multiple DataFrames


## Inner Merge
- The `.merge()` method looks for columns **that are common** between two DataFrames and then looks for rows where those column's values are the same.

```Python
new_df = pd.merge(orders, customers)
```

- In addition to the pandas `merge()`, each DataFrame has its own `merge()` method where you can merge columns.
```Python
new_df = orders.merge(customers)
```
>[!note] Produces the same dataframe

- This way is generally used when joining more than two DataFrames togther. We can "chain" the commands.

```Python
big_df = orders.merge(customers).merge(products)
```
>[!note] Merges orders to customers, and then the resulting DataFrame to products.

## Merge on Specific Columns
- When merging two dataframes there are times when columns may share the same generic column name like **id**
- The `rename()` offers the ability to rename columns.
```Python
pd.merge(orders, customers.rename(columns={'id': 'customer_id'}))
```

- Another option are the keywords `left_on` and `right_on`
- Specifies which columns we want to perform the merge on.
```Python
pd.merge(orders, customers, left_on='customer_id', right_on='id')
```
>[!note] The 'left' table is the one that comes first *orders* and the 'right' table is the one that comes second *customers*.
- Using the `suffixes` keyword we can provide a list of of suffixes to use to help name genric columns.
```Python
pd.merge(orders, customers, left_on='customer_id', right_on='id', suffixes=['_order', '_customer'])
```


## Outer Merge
- Merge all data from two or more dataframes.
```Python
pd.merge(dataframe_a, dataframe_b, how='outer')
```

## Left merge
- Includes all rows from the first, left table, but only rows from the second table that match the first table.
```Python
pd.merge(dataframe_a, dataframe_b, how='left')
```

## Right Merge
- The opposite of *left merge*. Includes all rows from the second table and only matching rows from the first table.
```Python
pd.merge(dataframe_a, dataframe_b, how='right')
```


## Concatenate DataFrames
- To construct a single DataFrame from multiple smaller DataFrames, there is the method `pd.concat()`
>[!warning] this methond only works if all the columns are the same in all the dataframes

```Python
pd.concat(df1, df2, df3)
```



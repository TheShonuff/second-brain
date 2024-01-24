---
tags:
  - python
  - pandas
---
# Panda Columns
## Getting Information
- `.info()` method will display a summary table of column information
- The `index` in the table is the column name `index` and not the actual DataFrame RangeIndex

- There are two methods for creating new columns
	- `DataFrame.assign()`
		- Creates a new DataFrame
- We can also create a new column using a dictionary like syntax
	- `df['New Column Name'] = [Values]`
- 
```Python
Month_Summary = Month_Summary.assign(Budgeted=0, Result=0, Month=date_month, Year=date_year)
```
>[!note] Adds four columns to the month summary DataFrame

- Using <code>DataFrame.insert()</code> we can specify the location of the column as well as the contents.
```Python
Month_Sumarry =  Month_Summary.assign(2,"Budgeted", [1500,1400,1300,1440], True)
```
>[!note] Inserts a column "Budgeted", in the "third" position with a list of values.

## Column Operations
- The `apply()` method can apply a function to every value in a particular column.
```Python
import pandas as pd

df = pd.read_csv('employees.csv')

get_last_name = lambda x: x.split(' ')[-1]
df['last_name'] = df['name'].apply(get_last_name)
```
>[!note] split's the name column and takes the last name. Creates a new column named *last_name* and *applies* the lambda function to the name column

- Multiple columns can be operated on at once. While using the `apply()` method an optional argument for axis can be supplied.
	- Use `axis=1` to apply to rows

## Renaming Columns
- All columns names can be changed at once using the `.columns` property.

```Python
df = pd.DataFrame({
		'name': ['John', 'Jane', 'Sue', 'Fred'],
		'age': [23,29,21,18]
})
df.columns = ['First Name', 'Age']
```

- Individual or multiple columns can be renamed using the `.rename` method.
	- `mapper=` accepts a dictionary that maps the old column names to the new names.

```Python
df = pd.DataFrame({
		'name': ['John', 'Jane', 'Sue', 'Fred'],
		'age': [23,29,21,18]
})
df.rename(columns={
		'name': 'First Name',
		'age': 'Age'},
		inplace=True)

column_mapper = {'name': 'First Name', 'age': 'Age'}
df.rename(mapper=column_mapper, axis=1)
```

- using `inplace=True` will modify the existing DataFrame without creating a new one.

## Removing Columns
- `.drop()` method will remove columns or rows.
	- Can accept a list of values.
```Python
df.drop(index='A', columns='B')
```
## Shift
- can be called on a single column or on the entire DataFrame.
![shift gif](https://content.codecademy.com/programs/python-for-finance/importing-finance-data/data-frame-shift.gif)
```Python
dataframe.shift(1)
```
>[!note] shifts all rows down by 1

```Python
dataframe['name'].shift[-5]
```
>[!note] shifts all rows in name column up 5

```Python
dataframe['price'].shift(3)
```
>[!note] shifts all rows in price column down 3


## Splitting Columns
- The syntax to split a column based on a delimiter
```Python
df['column'].str.split(pat=',', expand=True)
```
- **str** tells pandas we are treating the entires of a `column` as strings
- **split()** is a string method for splitting up strings
- **pat** patttern specifies the delimiter that splits the string
- **expand** paramater with the `True` argument returns a DataFrame with the strings split into columns.

## Combining Columns
- The syntax to combine a column
```Python
df['Combined'] = df['column_1'].str.cat(df['column_2'], sep=',')
```

## Removing Whitespaces
```Python
df['col1'] = df['col1'].str.strip()
```

## Replacing Characters
```Python
df['col1'] = df['col1'].str.replace(
									pat='old_pattern'
									repl='new_pattern'
									regex=False
)
```

## Changing DataTypes
```Python
df['col'] = df['col'].astype('type')
```
- **float64** decimal numbers
- **int64** for integers
- **object** for objects/text
- **category** for categorical data
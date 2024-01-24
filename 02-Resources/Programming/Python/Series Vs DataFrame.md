---
tags:
  - python
  - pandas
---

# Series Vs DataFrame

| Series                                                                       | DataFrame                                                               |
| ---------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| One-dimensional                                                              | Two-dimensional                                                         |
| Homogenous - Series elements must be of the same data type                   | Hererogenous - DataFrame elements can have different types              |
| Side-immutable - Once created, the size of a Series object cannot be changed | Size-mutable - Element can be dropped or added in an existing dataframe |

## Creating a DataFrame Using a series

```Python
data = pd.DataFrame({'Col1':pd.series([22,33,38])})
data
```

```Python
month_series_summary = Statement_DataFrame.groupby(["Classification"])["Amount"].sum()
month_summary = pd.DataFrame(month_series_summary)
```
>[!note] converts a series into a dataframe


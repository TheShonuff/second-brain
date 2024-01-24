---
title: Importing Finance Data
Created: 2023-11-26 22:50
tags:
  - python
aliases:
---

---
# Importing Finance Data
- There are several ways to get the data you need

## Import locally
```Python
data = pd.read_csv('data.csv')
```


## Datareader Module
- designed to interact with some of the world's most popular finance API's.
- [DataReader Github](https://github.com/pydata/pandas-datareader)

### Getting NASDAQ Symbols
- Datareader provides several functions for importing data from NASDAQ through the `nasdaq_trader` sub-module.

```Python
from pandas_datareader.nasdaq_trader import func
```

```Python
symbols = get_nasdaq_symbols()
```
>[!note] import list of stock symbols from `nasdqa_trader` sub-module

### Filtering Data by Date
- When importing data, it's useful to be able to specify exactly when we want it to be from.
- The `pandas_datareadder.data` sub-module has a `DataReader` function
```Python
import pandas_datareader.data as web

web.DataReader('Indentifier', 'name_of_api', start_date, end_date)
```

- The datatime module uses the format *(year, month, day)*

- Some services will want to use [[API Keys]]

## Calculating Basic Financial Statistics
- Two useful functions on financial data are **variance** and **covariance**.
- **Variance** measures how far a set of number are spread out from their average
	- Used to measure volatility
```Python
dataframe['stocks'].var()
```

- **Covariance** Describes the relationship between the returns on two different investments over a period of time.
```Python
dataframe.cov()
```


## Example
```Python
import codecademylib3_seaborn
import pandas as pd
import pandas_datareader.data as web
from datetime import datetime

apple_prices = pd.read_csv('apple_prices.csv')
print(apple_prices['open'].var())

start = datetime(2008,1,1)
end = datetime(2018,1,1)
gas_prices = web.DataReader('APUS12A74714', 'fred', start, end)

print(gas_prices)
```

---
title: Markowitz Mean-Variance Optimization (MVO)
Created: 2023-12-02 22:13
tags:
  - resources/finances
  - stocks
  - pandas
  - python
aliases:
---

---
# Markowitz Mean-Variance Optimization (MVO)
- An apporach how to allocate money between multiple assets by considering the risk return trade-off asset combinations
- Considers the expected returns and covariance of all assets.
- Will return a set of portfolios where:
	- The expected return is greater than any other with the same or lesser risk.
	- The risk is less than any other with the same expected return.


## Expected Return
- When stock data is downloaded, the information is formatted as asset values at the end of a period (daily, month, quarterly).
- Efficient frontiers, need to structure the data as a percent returned over each period.

>[!tip] Before a expected return of a portfolio is return, each asset needs to be calculated.

```Python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

path='stock_data.csv'
stock_data = pd.read_csv(path)

selected = list(stock_data.columns[1:])
quarterly_returns = stock_data[selected].pct_change()
expected_returns_avg = quarterly_returns.mean()
```

- `pct_change()` is used to calculate the quarterly returns.\
- When calculating the *efficient frontier*, we need the average expected return for each asset. 
	- `mean()` method is used to calculate the average

### Weight of an Asset
- The fraction of the money invested in the asset, divided by the total amount of money in the portfolio.
$$ W_n = {C_n \over total}$$

### Weighted sum 
- The *weighted sum of the return for each individual asset* helps calculate the return of a portfolio
$$ ER=w_1R_1 + W_2R_2 + W+3R+3 + W_4R_4$$

## Covariance Matrix
- The measure of an asset's unpredictability is called its risk. 
- Caculated using variance.
	- A high variance is considered risky.
- **Positive Covariance** - When one asset increases in value, the other usually increases in value. The covariance value will be greater than 0
- **Negative Covariance** - When one asset increases in value, the other usually decreases in value. The covariance value will be less than 0
- **Uncorrelated assets** - When there is no quantificable pattern to the response of two assets. The covariance value is equal to 0

- Values are stored in a covariance matrix.
- Easily calculated by calling the `.cov()` method on the calculated returns.
---
title: Python Financial Basics
Created: 2023-11-23 21:31
tags:
  - python
  - pandas
aliases:
---

---
# Python Financial Basics

## Simple Rate of Return
$$R = {E - S + D\over S}$$
- **R** - simple rate of return
- **S** - Starting price of investement
- **E** - Ending price of investment
- **D** - dividend

```Python
def calculate_simple_return(start_price, end_price, dividend=0):
	return ((end_price - start_price) + divident) / start_price
```

## Logarithmic Rate of Return
- Continously compounded return

$$ r = log(E) - log(S) = Log({E\over S}) $$
- **r** - Logarithmic rate of return
- **S** - starting price of investment
- **E** - ending price of investment

```Python
def calculate_log_return(start_price, end_price):
	return log(end_price / start_price)
```

>[!tip] Logarithmic is easier to make calculations about a single asses over time. Simple rate is easier for dealing with multiple assests over the same time period


## Aggregate Across Time 
### Approach I
- The time frame of the investment
- To convert a log rate of return from one time period to another, we can multiple the rate of return by the number of original time periods there are in the new time period.
$$ r = r_0 * t $$
- **r** - converted log rate of return
- **r0** - original log rate of return
- **t** - the number of original time periods in the new time period

>[!note] If we are converting dailty returns to annual returns, **t** may be *252* because that is typically the number of trading days in a year. If we are converting month returns to annual returns, **t** would be *12*

```Python
def annualize_return(log_return, time):
	return log_return * time
```

### Approach II
- An extension of the base formula
- Suppose we know the log rate of retunr for *5* days of a given year

$$r = {r_0 + r_0 + ... + r_0 \over n} * t$$
- **r** - converted log rate of return
- **r0** - The nth log return from the original time period
- **n** - the number of returns from the original time period
- **t** - the number of original time periods in the new time period

```Python
def convert_returns(log_retun, time):
	sum = 0
	for num in log_returns:
		sum += num
	return (sum / len(log_return)) * time
```

## Aggregate Accross Assets
- To learn the portfolio returns return would be simply the weighted average of each individual assets's simple rate of return.

$$ R = (W_1 + R_1) + (W_2 + R_2) ... (W_n + R_n)$$
- **R** portfolio simple return
- **W** weight of the nth investment in the portfolio
- **R** simple rate of return of the nth investment

- Weights of each asset is obtained by:
$$ W_i = {S_i \over S_1 + S_2 + ... S_n }$$
- **W** weight of the nth investment in the portfolio
- **S1** - starting price of the nth invesment in the portfolio

## Variance
- Key statistic for understanding *risk* is **variance**.
- A measure of the spread of a dataset, or how far apart each value is from the mean.
	- The greater the variance, the more spread out or variablee the data is.
$$σ^2 = {\sum(X_i - \bar X)^2 \over n}$$
- **σ^2** - variance
- **Xi** - the nth value in the dataset
- **X̄** - the mean of the dataset
- **n** - the number of values in the dataset

```Python
def calculate_variance(dataset):
	mean = sum(dataset) / len(dataset)
	numerator = 0
	for num in dataset:
		numerator += (num - mean) ** 2
	variance = numerator / len(dataset)
	return variance
```

### DataFrame Method
```Python
df['stocks'].var()
```

## Standard Deviation
- As an alternative to **variance**

$$ σ = \sqrt {\sum (X_I - \bar X) ^ 2 \over n} $$
- **σ** - Standard deviation
- **X1** - The nth value in the dataset
- **X̄** - The mean of the dataset
- **n** - the number of values in the dataset

```Python
def calculate_variance(dataset):
	mean = sum(dataset) / len(dataset)
	numerator = 0
	for num in dataset:
		numerator += (num - mean) ** 2
	variance = numerator / len(dataset)
	return variance

def calcuate_stddev(dataset):
	vairance = calculate_variance(dataset)
	stddev = sqrt(vairance)
	return stddev
```

## Correlation I
- An important statistic for assessing risk.
- A measure of how closely two datasets are associated with each other.
- Represent by the *correlation coefficient*
	- A value between `-1` and `1`
	- Indiciating a positive or negative correlation
- **Positive Correlation** When the rate of return of one asset deviates upward from its mean, the other usually deviates upware as well
- **Negative Correlation** When the rate of return of one asset deviates upward from its mean, the other usually deviates downward.
- **No Correlation** When a change in one asset's rate of return does not dictate a change in another. The correlation coefficeinet will be close to zero.

### Pearson Correlation Coefficient
$$ r_{xy} = {n * \sum (X_1 * Y_1) - \sum X_1 * \sum Y_1 \over \sqrt {n * \sum X^2_i - (\sum X_i)^2} \sqrt {n * \sum Y^2_i - (\sum Y_i)^2}} $$
- $r_{xy}$ Correlation coeffiecient
- $X_i$ The nth value in dataset X
- $Y_i$ The nth value in dataset Y
- $n$ The number of values in the dataset.
```Python
def calculate_correlation(set_x, set_y):
	sum_x = sum(set_x)
	sum_y = sum(set_y)

	sum_x2 = sum([x **2 for x in set_x])
	sum_y2 = 0
	for y in set_y:
		sum_y2 += y ** 2
	
	sum_xy = 0
	for i in range(len(set_x)):
		sum_xy += set_x[i] * set_y[i]

	n = len(set_x)

	numerator = n * sum_xy - sum_x * sum_y
	denominator = sqrt((n * snum_x2 - sum_x ** 2) * (n * sum_y2 - sum_y ** 2))
	return numerator / denominator
```

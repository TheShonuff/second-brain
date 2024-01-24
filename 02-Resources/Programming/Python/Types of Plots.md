---
title: Types of Plots
Created: 2023-11-30 21:09
tags:
  - python
  - matplotlib
aliases:
---
# Types of Plots

## Bar Chart
- `plt.bar` creates simple bar charts to compare categories of data.
	- clled with two arguments
		- x-value
		- y-value
- [[Subplot|Subplots]] are created in the same way.
>[!tip] Set `set_xticks` before `set_xticklabels`


```Python
from matplotlib import pyplot as plt

drinks = ["cappuccino", "latte", "chai", "americano", "mocha", "espresso"]
sales = [91, 76, 56, 66, 52, 27]

plt.bar(range(len(drinks)), sales)

ax = plt.subplot()
ax.set_xticks(range(len(drinks)))
ax.set_xticklabels(drinks)

plt.show()
```

### Side-By-Side Bars
- Used to compare two sets of data with the same types of axis values.
- Uses list comprehensions to generate values from a list of variables
	- `n` = the dataset number
	- `t` = total number of dataset
	- `d` = number of sets of bars
	- `w` = Width of each bar
	- `[t*element + w*n for element in range(d)]`


```Python
drinks = ["cappuccino", "latte", "chai", "americano", "mocha", "espresso"]
sales1 = [91, 76, 56, 66, 52, 27]
sales2 = [65, 82, 36, 68, 38, 40]

n = 1
t = 2
d = 6
w = 0.8
store1_x = [t*element + w*n for element in range(d)]
plt.bar(store1_x,sales1)

n = 2
t = 2
d = 6
w = 0.8
store2_x = [t*element + w*n for element in range(d)]
plt.bar(store2_x, sales2)
  
plt.show()
```

### Stacked Bars
- Compare two sets of data while preserving knowledge of the total between them.
- Add the `bottom` keyword to `plt.bar()` 
- Graph the first set of data
- Garph the second set of data and explicity set the first set as bottom

```Python
drinks = ["cappuccino", "latte", "chai", "americano", "mocha", "espresso"]
sales1 = [91, 76, 56, 66, 52, 27]
sales2 = [65, 82, 36, 68, 38, 40]

plt.bar(range(len(drinks)), sales1)
plt.bar(range(len(drinks)), sales2, bottom=sales1)
plt.legend(['Location 1', 'Location 2'], loc=0)

plt.show()
```

### Error Bars
- Visually communicate an uncertainty in the height of bars.
- `yerr=` will set the y-axis error +/- amount
	- can be assigned to a list as well.
- `capsize` will adjust the width of the upper and lower bars on the line.


## Line Plots Fill Between
- Margin of error displayed on line graphs.
- `plt.fill_between()` takes three arguments
	- x-values
	- lower-bound for y-values
	- upper-bound for y-values
- The `alpha=` keyword is used to display opacity.
- Use a list comprehension to generate upper and lower bounds.

```Python
months = range(12)
month_names = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
revenue = [16000, 14000, 17500, 19500, 21500, 21500, 22000, 23000, 20000, 19500, 18000, 16500]

plt.plot(months, revenue)
ax=plt.subplot()
ax.set_xticks(months)
ax.set_xticklabels(month_names)
  
y_lower = [i - .1 * i for i in revenue]
y_upper = [i + .1 * i for i in revenue]

plt.fill_between(revenue, y_lower, y_upper, alpha=.2)

plt.show()
```

## Pie Chart
- Helpful to display elements of a data set as a proportions of a whole
- `plt.pie()`
- When pie charts are shown they'll be displayed titled
	- used `plt.axis('equal')` to flatten the chart.
```Python
payment_method_names = ["Card Swipe", "Cash", "Apple Pay", "Other"]
payment_method_freqs = [270, 77, 32, 11]

plt.pie(payment_method_freqs)
plt.axis('equal')

plt.show()
```

### Labeling Pie Charts
- use `plt.legend()` to display the values in a pie chart.
- The keyword `labels=` is a helpful shortcut.
- `autopct=` a useful keyword for adding a *percentage total*.
	- uses [string formatting](https://docs.python.org/2/library/stdtypes.html#string-formatting) operations.
```Python
payment_method_names = ["Card Swipe", "Cash", "Apple Pay", "Other"]
payment_method_freqs = [270, 77, 32, 11]

plt.pie(payment_method_freqs, autopct='%0.1f%%')
plt.axis('equal')
plt.legend(payment_method_names)

plt.show()
```

## Histogram
- Displays how many values in a dataset fall between different sets of numbers.
- `plt.hist()`
- finds the minimum and maximum values in a dataset and creates 10 equally-spaced bins between those values.
	- If more bins are desired use keyword `bins=`

### Multiple Histograms
- Comparing different distributions
- use `plt.hist()` to plot the additional set of data
	- use the same number of `bins=`
- `alpha=` is used to see through overlapping areas.
- `density` normalizes the data
- `histtype` can redraw the display type of a histogram.
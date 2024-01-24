---
title: Matplotlib
Created: 2023-11-27 22:14
tags:
  - python
  - matplotlib
aliases:
---
# Matplotlib
- Python library for creating charts and graphs

```Python
x_values = [0,1,2,3,4]
y_values = [0,1,4,9,16]
plt.plot(x_values, y_values)
plt.show()
```
>[!note] Basic line graph 

## Linestyles
- Line colors can be specified using the keyworkd `color` 
```Python
plt.plot(x_values,y_values, color='#AAAAAA')
plt.plot(x_values,y_values, color='green')
```
- Other keywords than can be used are
	- `linestyle` changes the line look
	- `marker` as a market when the line changes
		- full list of markers in [documentation](https://matplotlib.org/stable/api/markers_api.html)
			- Common Markers
				- `"."` point
				- `","` pixel
				- `"o"` circle
					

## Axis and Labels
### Axis
- To zoom in or out of the plot we can use `plt.axis()`
- The method accepts a list as input
	- The minimum x-value displayed
	- the maximum x-value displayed
	- the minimum y-value displayed
	- the maximum y-value displayed

### Labels
- Labels are added use two methods. Each method accepts a string.
	- `plt.xlabel()`
	- `plt.ylabel()`


## Legends
- Multiple lines on a single graph can be labeled with a legend
	- `plt.legend()`
- Can  take the keyword `loc` to position the legend

| Number Code | String       |
| ----------- | ------------ |
| 0           | best         |
| 1           | upper right  |
| 2           | upper left   |
| 3           | lower left   |
| 4           | lower right  |
| 5           | right        |
| 6           | center left  |
| 7           | center right |
| 8           | lower center |
| 9           | upper center |
| 10          |              |

```Python
legend_labels = ["Hyrule", "Kakariko", "Gerudo Valley"]
plt.legend(legend_labels, loc=8)
```

## Modify Ticks
```Python
ax = plt.subplot()
ax.set_xticks(months)
ax.set_xticklabels(month_names)
ax.set_yticks([.10,.25,.5,.75])
ax.set_yticklabels(['10%', '25%', '50%', '75%'])
```

## Figures
```Python
plt.figures(figsize=(4,10))
plt.plot(x, parabola)
plt.savefig('tall_and_narror.png')
```
>[!note] a new figure with a width of 4 inchs and a height of 10 inches

- Figures can be saved with the `plt.savefig()` method with a supplied string as the file name.
	- Supports png, svg and pdf



# Examples

## Sublime Limes
```Python
import codecademylib
from matplotlib import pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
visits_per_month = [9695, 7909, 10831, 12942, 12495, 16794, 14161, 12762, 12777, 12439, 10309, 8724]

key_limes_per_month = [92.0, 109.0, 124.0, 70.0, 101.0, 79.0, 106.0, 101.0, 103.0, 90.0, 102.0, 106.0]
persian_limes_per_month = [67.0, 51.0, 57.0, 54.0, 83.0, 90.0, 52.0, 63.0, 51.0, 44.0, 64.0, 78.0]
blood_limes_per_month = [75.0, 75.0, 76.0, 71.0, 74.0, 77.0, 69.0, 80.0, 63.0, 69.0, 73.0, 82.0]

  
plt.figure(figsize=(12,8))
ax1 = plt.subplot(1,2,1)
x_values = range(len(months))
ax1.plot(x_values, visits_per_month, marker='o')
ax1.set_xticklabels(months)
ax1.set_xticks(x_values)
plt.xlabel('Months')
plt.ylabel('Number of visits')
plt.title('Visits to Farm')

ax2 = plt.subplot(1,2,2)
ax2.plot(x_values, key_limes_per_month, marker='o', color='green')
ax2.plot(x_values, persian_limes_per_month, marker='o', color='purple')
ax2.plot(x_values, blood_limes_per_month, marker='o', color='red')
plt.legend(['Key Limes', 'Persian Limes', 'Blood Limes'], loc=0)
ax2.set_xticklabels(months)
ax2.set_xticks(x_values)
plt.xlabel('Months')
plt.ylabel('Limes Sold')
plt.title('Limes Sold at Farm')

plt.show()
plt.savefig('Limes_sold_on_farm.png')
```


![[Pasted image 20231130210830.png]]

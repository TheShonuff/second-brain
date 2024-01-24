---
title: Subplot
Created: 2023-11-29 22:21
tags:
  - python
  - matplotlib
aliases:
---

# Subplot
- Multiple axes in the same picture
- Created using the `subplot()` method
- Requires three arguments to be passed into it
	- the number of rows of subplots
	- the number of columns of subplots
	- the index of the subplot we want to create
- `plt.subplot(2,3,4)` would create the *Subplot 4* in the image below
![[Pasted image 20231129222216.png]]
>[!note] six subplots split into 2 rows and 3 columns

>[!tip] any `plt.plot()` after a `plt.subplot()` will create a line plot in the specified subplot.

## Spacing
- **left** the left-sided margin. Default is 0.125
- **Right** The right-sided margin. Default is 0.9
- **Bottom** The bottom margin. Default is 0.1
- **Top** The top margin. Default is 0.9
- **wspace** The horizontal space between adjacent subplots. Default is 0.2
- **hspace** The vertical space between adjacent subplots. Default is 0.2

## Modify Ticks
```Python
ax = plt.subplot()
ax.set_xticks(months)
ax.set_xticklabels(month_names)
ax.set_yticks([.10,.25,.5,.75])
ax.set_yticklabels(['10%', '25%', '50%', '75%'])
```

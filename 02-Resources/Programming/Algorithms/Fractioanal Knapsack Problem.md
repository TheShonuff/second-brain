---
title: Fractioanl Knapsack Problem
Created: 2023-11-18 20:59
tags:
  - python
  - algorithms
aliases:
---

---
# Fractioanal Knapsack Problem
- We are given a set of $N$ items. Each item $i$ has a value and a weight $w$.
	- $0<=i<n$
	- We are given a maximum weight $W$
- The probelm is to find how much of each item we should take such that the total weight does not exceeed $W$ and the total value in maximized.

## Problem Solution
- The function fractional_knapsack is defined
- It takes three arguments, two lists value and weight; and a number capacity.
- It returns (max_value, fractions) where max_value is the maximum value of items with total weight not more than capacity.
- Fractions is a list where `fractions[i]` is the fraction that should be take of item $i$ 
- The function works by choosing an item from the remaining items that has the maximum  value to weight ratio.
- If the knapsack can include the entire weight of the item, then the full amount of the item is added to the knapsack
- If not, then only a fraction of this item is added such that the knapsack becomes full.
- The above three steps are repeated until the knapsack becomes full, or the total weight reaches the maximum weight.

```Python
def fractioanl_knpsack[value, weight, capacity]:
	index = list(range(len(value)))
	ratio = [v/w for v, w in zip(value, weight)]
	index.sort(key=lambda i: ratio[i], reverse=True)

	max_value = 0
	fractions = [0]*len(value)
	for i in index:
		if weight[i] <= capacity:
			fractions[i] = 1
			max_value += value[i]
			capacity -= weight[i]
		else:
			fractions[i] = capacity/weight[i]
			max_value += value[i]*capacity/weight[i]
			break
	return max_value, fractions
```

## CIS256 Implementation
- complexity is $O(nlogn)$
```Python
class Food(object):
	def __init__(self, name, value, weight):
		self.name = name
		self.value = value
		self.calories = weight
	def get_value(self):
		return self.value
	def get_cost(self):
		return self.calories
	def density(self):
		return self.get_value()/self.get_cost()
	def __str__(self):
		return self.name + ': <' + str(self.value) + ', ' + str(self.calories) + '>'
```

```Python
def build_menu(names, values, calories):
	menu = []
	for i in range(len(values)):
		menu.append(Food(names[i], values[i], calores[i]))
	return menu
```

```Python
def knapsack(items, max_cost, key_function):
	items_copy = sorted(items, key = key_function, reverse = True)
	result = []
	total_value, total_cost = 0.0,0.0
	for i in range(len(items_copy)):
		if (total_cost + items_copy[i].get_cost()) <= max_cost:
			result.append(items_copy[i])
			total_cost += items_copy[i].get_cost()
			total_value += items_copy[i].get_value()
	return (result, total_value)
```


---
tags:
  - python
  - numpy
---

# NumPy

## Arrays
- A **NumPy** array is a special type of list that can organize multiple items.
	- Each item can be any data type.
```Python
my_array = np.array([1,2,3,4,5,6])

my_list = [1,2,3,4,5,6]
my_array = np.array(my_list)
```

- Array's can be generated from imported CSV files using `genfromtxt` method
```Python
csv_array = np.genfromtxt('sample.csv', delimiter=',')
```

### Operation with NumPy Array
- Allows *element-wise operations* easily without a for loop or [[Python List Comprehensions|list comprehension]].
```Python
test_1 = np.array([92, 94, 88, 91, 87])
test_2 = np.array([79, 100, 86, 93, 91])
test_3 = np.array([87, 85, 72, 90, 92])

test_3_fixed = test_3 + 3
```
>[!note] Adds three points to each test score.

- Whole arrays can be added or subtracted from each other

#### Selecting Elements
- Can select elements from an array using the indices.
- Same rules apply for slicing and indexing as regular lists.
### Two-Dimensional Arrays
```Python
np.array([[92, 94, 88, 91, 87],    
		  [79, 100, 86, 93, 91],          
		  [87, 85, 72, 90, 92]])
```

![[Pasted image 20231125143101.png]]
#### Selecting Elements
- The syntax is slightly different.
- **axis=0** are the values that share an index
- **axis=1** are the values that share an array
- `arr[r,c]`
	- `r` row
	- `c` column
	 ![[Pasted image 20231125202801.png]]
```Python
a = np.array([[32, 15, 6, 9, 14],               
			  [12, 10, 5, 23, 1],              
			  [2, 16, 13, 40, 37]])
```

- We can select specific elements using their indices `a[2,1]` yields `16`
- Select an entire column, we can insert `:` as the row index.
	- `a[:,0]` yields `[32, 12, 2]`
- The same works for an entire row
	- `a[1,:]` yields `[12, 10, 5, 23, 1]`
- It can be narrowed down to a range in a row
	- `a[0,0:3]` yields `[32, 15, 6]`

## Logical Operations
- Can perform *element-wise logical operations* that doesn't require a for loop

```Python
a = np.array([10, 2, 2, 4, 5, 3, 9, 8, 9, 7])
a > 5
array([True, False, False, False, False, False, True, True, True, True], dtype=bool)
```

- We can use logical operators to evaluate and select items based on certain criteria

```Python
a[a > 5]
array([10, 9, 8, 9, 7])
```

- We can use logical statements to further specify the criteria.

```Python
a[(a > 5) | (a < 2)]
array([10, 9, 8, 9, 7])
```


Numerical Python
- Internally sores data in a contiguous block of memory, indepedent of other built-in Python objects.

- [[ndarray]]




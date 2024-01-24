---
tags:
  - python
---
# ndarray
- N-dimensional array object.
- A generic multidimensional container for homogeneous data.
- Fast, flexible container for large datasets in Python.

- **Shape** ( number of dimensions, items in each dimension)
- Can explicitly convert or cast an array from data type to another using <code>astype()</code> method.
	- Always creates a new array ( a copy of the data) even if the new data type is the same as the old data type.
```Python
arr = np.array([1,2,3,4,5])
float_arr = arr.astype(np.float64)
```
> [!note] Cast int as float64. For a full list of [[Numpy Data Types]]

## Arithmetic
- Enables batch operations on data without writing any for loops.
- Called **vectorization**
- Any arithmetic operations between equal-szied arrays apply the operations element-wise
- Evaulating operatings between different sized arrays is called **broadcasting**

## Indexing & Slicing
- One dimensional arrays are similiar to regular Python lists.
	- Array slices are views on the original array. 
		- Data is not copied
		- All modifications to the view will be reflected in the source array.
		- If you want a copy you will need to explicitly copy the array.
	- The "bare" slice <code>[:]</code> will assign to all values in the array.
- Higher dimension arrays
	- Two-dimensional array
		- Elements are no longer scalars but one-dimensional arrays
		- A comma seperated list of indices to select individual elements. <code>arr[0,1]</code>
		- Helpful to think of it as *row, column*
	- multi-dimension array
		- Omitting later indices returns a object of the lower dimensional ndarray.

## Universal Functions
- A *ufunc* is a function that performs element-wise operationgs on data in ndarrays.
	- Examples include: sqrt,square,log,log10,floor
- binary *unfuc* takes two arrays and returns a single array.
	- Examples include: add, subtract, multiply, maximum




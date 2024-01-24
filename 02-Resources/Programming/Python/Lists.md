---
tags:
  - python
---
# Lists
- A **container** created by surrounding a sequence of variables or literals with brackets
- A list is **mutable**.
- Can have mixed types.
- Lists can be accessed with an integer.
	- Floating point numbers can not be used.
- Lists can contain different data types.

```Python
list.method(input)
```
## Adding and Removing Elements
- The `append()` method is used to add new elements to the end of a list
- `pop()` removes element at a given index or the end of the list.
- `remove()` removes the first element with a given value
- `insert()` insert an element into a specific index

### Sequence-type functions
- Bult-in functions that operate

| Operation         | Description                                                             |
| ----------------- | ----------------------------------------------------------------------- |
| `len(list)`       | Find the length of a list                                               |
| list1 + list2     | Produce a new list by concatenating list2 to end of list1               |
| `min(list)`       | Find the smallest value in a list                                       |
| `max(list)`       | Find the maximum value in a list                                        |
| `sum(list)`       | Find the sum of all elements of a list (numbers only)                   |
| `list.index(val)` | Find the index of the first element in the list whose value matches val |
| `list.count(val)` | Count the number of occurrences of the value val in the list            |


### Ways to create a list
```Python
my_list = [1,2,3]

my_list = list(1,2,3)

```

### Accessing List Elements
- An **index** is a zero-based integer matching to a specifci position in the list's sequence of elements.

### Common List Operations
- **In-place modification** is the growing and shrinking of a list without creating a copy of the list.
- A **list method** can perform useful operations on alist such as adding or removing elements, sort, reversing, etc.

| List Method            | Description                                         |
| ---------------------- | --------------------------------------------------- |
| **Adding Elements**    |                                                     |
| list.append(x)         |                                                     |
| list.extend(x)         | Add all items [x] to list                           |
| list.insert(i,x)       | Insert x into list before position i                |
| **Removing Elements**  |                                                     |
| list.remove(x)         | Remove first item from list with value x            |
| list.pop()             | Remove and return last item in list                 |
| list.pop(i)            | Remove and reuturn item at postion i in list        |
| **Modifying Elements** |                                                     |
| list.sort()            | Sort he items of list in-place                      |
| list.reverse()         | Reverse the elements of the list in-place           |
| **Miscellaneous**      |                                                     |
| list.index(x)          | Return the index of first item in list with value x |
| list.count(x)          | Count the number of times value x in in list        |


### Removing all instances from a list
- Using list comphresion we can remove all instances from a list
```Python
x = [i for i in list if i !="word"]
```

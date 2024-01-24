---
title: Container Wrappers
Created: 2023-10-24 20:47
tags:
  - python
aliases:
---
# Container Wrappers
- Wrappers are modifications to functions or classess.


## UserDict
- Lets the developer create their own version of a dictionary.
- Contains all the functionality of a normal dictionary.
- Data can be accessed through the `data` property.
```Python
from collections import UserDict

class DisplayDict(UserDict):
	def display_info(self):
		print('Number of Keys ' + str(len(self.keys())))
		print('Keys: ' + str(list(self.keys())))
		print('Number of Values: ' + str(len(self.values())))
		print('Values: ' + str(list(self.values())))
	def clear(self):
		print('Deleting all items from the dictionary')
		super().clear()

disp_dict = DisplayDict({'user': 'Mark', 'device': 'desktop', 'num_visits': 37})
disp_dict.display_info()
disp_dict.clear()
```

```Python
from collections import UserDict

data = {'order_4829': {'type': 't-shirt', 'size': 'large', 'price': 9.99, 'order_status': 'processing'},
'order_6184': {'type': 'pants', 'size': 'medium', 'price': 14.99, 'order_status': 'complete'},
'order_2905': {'type': 'shoes', 'size': 12, 'price': 22.50, 'order_status': 'complete'},
'order_7378': {'type': 'jacket', 'size': 'large', 'price': 24.99, 'order_status': 'processing'}}


class OrderProcessingDict(UserDict):
	def clean_orders(self):
		del_items = []
		for order in self.data:
			if self.data[order]['order_status'] == 'complete':
				del_items.append(order)

		for order in del_items:
			del self.data[order]

process_dict = OrderProcessingDict(data)
process_dict.clean_orders()
```
## UserList
- Lets the developer create their own version of a list.
```Python
from collections import UserList

data = [4, 6, 8, 9, 5, 7, 3, 1, 0]

# Write your code below!
class ListSorter(UserList):
	def append(self, value):
		self.data.append(value)
		self.data.sort()

sorted_list = ListSorter(data)
sorted_list.append(2)
```

## UserString

```Python
from collections import UserString
str_name = 'python powered patterned products'
str_word = 'patterned '

class SubtractString(UserString):
	def __sub__(self,other:str):
		if other in self.data:
			self.data = super().replace(other,'')

return self

  
  

subtract_string = SubtractString(str_name)

subtract_string - str_word
```



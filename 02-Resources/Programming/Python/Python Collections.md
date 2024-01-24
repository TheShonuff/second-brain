---
title: Python Collections
Created: 2023-10-23 21:07
tags:
  - python
aliases:
---

---
# Python Collections
- classess from the `collections` module are very similar to the built-in containers but they contain new methods and utilities.

```Python
import collections

from collections import *

from collections import name_of_class, name_of_another_class
```
>[!note] There are several ways to import the collections module

```Python
from collections import OrderedDict

orders = OrderedDict({'order_4829':{'type': 't-shirt','size':'large', 'price': 9.99},
					 'order_6184':{'type':'pants', 'size':'medium','price': 14.99},
					 'order_2905': {'type':'shoes','size':12,'price':22.50}})
orders.move_to_end('order_4829')
orders.popitem()
```


## deque
- similar to list but they are optimized for appending and popping to the front and back.
- Best if you don't need to work with data from the middle.
- For all methods refer to the Python [documentation](https://docs.python.org/3/library/collections.html#collections.deque)
```Python
from collections import deque

bug_data = deque()

loaded_bug_reports = get_all_bug_reports()

for bug in loaded_bug_reports:
	if bug['priority'] == 'high':
		bug_data.appendleft(bug)
	else:
		bug_data.append(bug)

next_bug_to_fix = bug_data.popleft()
```

## namedtuple
- Allows for an immutable tuple object.
- Every element is self documented.
- Returns a subclass and naming convetion should use **CapWords**
```Python
from collections import nametuple

ActorData = namedtuple('ActorData', ['name', 'birth_year', 'movie', 'movie_release_date'])

actor_data = ActorData('Leonardo DiCaprio', 1974, 'Titanic', 1997)

print(actor_data.name)
```

## counter
- count instances of an element in a collection.
- Refer to the [documentation](https://docs.python.org/3/library/collections.html#collections.Counter) for more utility classes.
```Python
from collections import Counter

counted_items = Counter[clothes_list]
print(counted_items)
```

```Python
from collections import Counter

opening_inventory = ['shoes', 'shoes', 'skirt', 'jeans', 'blouse', 'shoes', 't-shirt', 'dress', 'jeans', 'blouse', 'skirt', 'skirt', 'shorts', 'jeans', 'dress', 't-shirt', 'dress', 'blouse', 't-shirt', 'dress', 'dress', 'dress', 'jeans', 'dress', 'blouse']

closing_inventory = ['shoes', 'skirt', 'jeans', 'blouse', 'dress', 'skirt', 'shorts', 'jeans', 'dress', 'dress', 'jeans', 'dress', 'blouse']

def find_amount_sold(opening, closing, item):
	opening_count = Counter(opening)
	closing_count = Counter(closing)
	opening_count.subtract(closing_count)
	return opening_count[item]

tshirts_sold = find_amount_sold(opening_inventory, closing_inventory, 't-shirt')

print(tshirts_sold)
```
## Dictionary Collections
### defaultdict
- A solution to missing key values in dictionaries
- Default value can be assigned using a lambda expression
	- instead of a KeyError the expression will be printed.
- Refer to the Python [documentation](https://docs.python.org/3/library/collections.html#collections.defaultdics)
```Python
from collections import defaultdict

validate_prices = defaultdict(lambda: 'No Price Assigned')

validate_prices['jeans'] = 19.99
validate_prices['shoes'] = 24.99
validate_prices['t-shirt'] = 9.99
validate_prices['blouse'] = 19.99
```

```Python
from collections import defaultdict

site_locations = {'t-shirt': 'Shirts',
	'dress shirt': 'Shirts',
	'flannel shirt': 'Shirts',
	'sweatshirt': 'Shirts',
	'jeans': 'Pants',
	'dress pants': 'Pants',
	'cropped pants': 'Pants',
	'leggings': 'Pants'
}

updated_products = ['draped blouse', 'leggings', 'undershirt', 'dress shirt', 'jeans', 'sun dress', 'flannel shirt', 'cropped pants', 'dress pants', 't-shirt', 'camisole top', 'sweatshirt']

# Write your code below!
validated_locations = defaultdict(lambda: 'TODO: Add to website')
  
validated_locations.update(site_locations)

for product in updated_products:
	if product not in site_locations:
		site_locations[product] = validated_locations[product]

print(site_locations)
```

### OrderedDict
- Allows access to values using keys and preseves the order of the elements.
- Refer to the Python [Documentation](https://docs.python.org/3/library/collections.html#collections.OrderedDict)
```Python
from collections import OrderedDict

orders = OrderedDict()
```

```Python
from collections import OrderedDict

# The first 15 orders are provided
order_data = [['Order: 1', 'purchased'],
['Order: 2', 'purchased'],
['Order: 3', 'purchased'],
['Order: 4', 'returned'],
['Order: 5', 'purchased'],
['Order: 6', 'canceled'],
['Order: 7', 'returned'],
['Order: 8', 'purchased'],
['Order: 9', 'returned'],
['Order: 10', 'canceled'],
['Order: 11', 'purchased'],
['Order: 12', 'returned'],
['Order: 13', 'purchased'],
['Order: 14', 'canceled'],
['Order: 15', 'purchased']]

# Write your code below!
orders = OrderedDict(order_data)
to_move = []
to_remove = []

for i, (key, value) in enumerate(orders.items()):
	if i <= len(orders):
		if value == 'returned':
			to_move.append(key)
		elif value == 'canceled':
			to_remove.append(key)
	else:
		break

for item in to_remove:
	ordeqrs.popitem(item)

for item in to_move:
	orders.move_to_end(item)

print(orders)
```

### ChainMap
- Allows to store many mappings in an ordered group.
- Treats all stored dictionaries as one large dictionary.
- Initialize the `ChainMap` with the mappings which we want to use.
```Python
from collections import ChainMap

year_profit_data = [
	{'jan_profit': 15492.30, 'jan_holiday_profit': 2589.12},
	{'feb_profit': 17018.05, 'feb_holiday_profit': 3701.88},
	{'mar_profit': 11849.13},
	{'apr_profit': 9870.68},
	{'may_profit': 13662.34},
	{'jun_profit': 12903.54},
	{'jul_profit': 16965.08, 'jul_holiday_profit': 4360.21},
	{'aug_profit': 17685.69},
	{'sep_profit': 9815.57},
	{'oct_profit': 10318.28},
	{'nov_profit': 23295.43, 'nov_holiday_profit': 9896.55},
	{'dec_profit': 21920.19, 'dec_holiday_profit': 8060.79}
]

new_months_data = [
	{'jan_profit': 13977.85, 'jan_holiday_profit': 2176.43},
	{'feb_profit': 16692.15, 'feb_holiday_profit': 3239.74},
	{'mar_profit': 17524.35, 'mar_holiday_profit': 4301.92}

]
# Write your code below
profit_map = ChainMap(*year_profit_data)

def get_profits(chainmap):
	holiday_profits = 0
	regular_profits = 0
	for key, value in chainmap.items():
		if 'holiday' in key:
			holiday_profits += value
		else:
			regular_profits += value
	return regular_profits, holiday_profits

last_year_standard_profit, last_year_holiday_profit = get_profits(profit_map)
print(f'last years standard profits ${last_year_standard_profit}\nlast year holiday profit ${last_year_holiday_profit}')

profit_map = ChainMap(*new_months_data, *profit_map.maps)
  
current_year_standard_profit, current_year_holiday_profit = get_profits(profit_map)

year_diff_standard_profit = current_year_standard_profit - last_year_standard_profit

year_diff_holiday_profit = current_year_holiday_profit-last_year_holiday_profit

print(year_diff_standard_profit)
print(year_diff_holiday_profit)
```
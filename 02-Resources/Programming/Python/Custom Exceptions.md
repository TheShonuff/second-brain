---
title: Custom Exceptions
Created: 2023-10-18 22:26
tags:
  - python
  - error-handling
aliases:
---
# Custom Exceptions
- User-defined exception are exceptions that allow for better readability
- Derive a subclass from the **Exception** class.

```Python
class CustomError(Exception)
	pass
```

- A custom class an accept arguments and output data based on the supplied arguments.
### Example
```Python
class LocationTooFarError(Exception)L
	def __init(self, distance)
		self.distance = distance
	def __str__(self):
		return 'Location is not within 10km'

def schedule_delivery(distance_from_store):
	if distance_from_store > 10:
		raise LocationTooFarError(distance_from_store)
	else:
		print('Scheduling the delivery...')
```




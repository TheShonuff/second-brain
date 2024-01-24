---
tags:
  - python
---

# Tuple
- Stores a collection of data like a list but is **immutable**
- Are surrounded by parentheses
- Used when element position is important.

## Named Tuples
- Allows the programmer to define a new simple data type that consists of name attributes.
- The **nametuple** module needs to be imported.

```Python
from collections import namedtuple

Car = namedtuple('Car', ['make','model','price','horsepower','seats'])  # Create the named tuple

chevy_blazer = Car('Chevrolet', 'Blazer', 32000, 275, 8)  # Use the named tuple to describe a car
chevy_impala = Car('Chevrolet', 'Impala', 37495, 305, 5)  # Use the named tuple to describe a different car

print(chevy_blazer)
print(chevy_impala)
#Output
Car(make='Chevrolet', model='Blazer', price=32000, horsepower=275, seats=8)
Car(make='Chevrolet', model='Impala', price=37495, horsepower=305, seats=5)
```

## Unpacking
- The process that performs multiple assignments at once.
- Binding comma seperated names on the left to the elements of a sequence on the right.
```Python
num1,  num2 = (250, 100)
```

> [!note] Can also be use to unpack lists


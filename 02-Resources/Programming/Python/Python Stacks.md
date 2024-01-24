---
title: Python Stacks & Queus
Created: 2023-10-01 14:38
tags:
  - python
aliases:
---

---
# Python Stacks 
- Implementation [[Stacks]] in Python takes some consideration.
- Contains an ordered set of data.
- Three methods for interaction
	- Push
	- Pop
	- Peek

>[!tip] should be implemented using a [[Linked List]] for effeciency

>[!tip] Last in, first out

>[!warning] You do not traverse a stack
## Abstract Data Type
- `Stack()` creates a new stack that is empty
- `push()` add item to top
- `pop()` remove item from the top
- `peek()` return reference to top item.
- `isEmpty()` tests to see whether the stack is empty. returns a boolean
- `size()` returns the number of items on the stack. Returns an integer
## Stack Class with List(Array)
```Python
class Stack:
	def __init__(self):
		self.items = []
		
	def isEmpty(self):
		return self.items == []
		
	def push(self, item):
		self.items.append(item)
		
	def pop(self):
		return self.items.pop()
		
	def peek(self):
		return self.items[lens(self.items)-1]
		
	def size(self)
		return len(self.items)
```

## Stack Class With Linked List
```Python
from node import Node

class Stack:
	def __init__(self, limit=1999):
		self.top_item = None
		self.size = 0
		self.limit = limit
		
	def push(self,value):
		if.self.has_space():
			item = Node(value)
			item.set_next_node(self.top_item)
			self.top_item = item
			self.size += 1
		else:
			print("No room")
		
	def pop(self):
		if not self.is_empty():
			item_to_remove = self.top_item
			self.top_item = item_to_remove.get_next_node()
			self.size -= 1
			return item_to_remove.get_value()
		print("Nothing left")
		
	def peek(self):
		if not self.is_empty():
			return self.top_item.get_value()
		print("Nothing to see here!")
```

### Helper methods
```Python
	def has_space(self):
		if self.limit > self.size:
			return True
	def is_empty(self):
		if self.size == 0:
			return True
```
# Examples
## Balanced Parenthese 
```Python
def parChecker(symbolString):
	s = Stack()
	balanced = True
	index = 0
	while index < len(symbolString) and balanced:
		symbol = symbolString[index]
		if symbol == "(":
			s.push(symbol)
		else:
			if s.isEmpty():
				balanced = False
			else:
				s.pop()
		index = index + 1
	if balanced and s.isEmpty()
		return True
	else:
		return False
```

### Checking Multiple Bracket Types
```Python
def parChecker(symbolString):
    s = Stack()
    balanced = True
    index = 0
    while index < len(symbolString) and balanced:
        symbol = symbolString[index]
        if symbol in "([{":
            s.push(symbol)
        else:
            if s.isEmpty():
                balanced = False
            else:
                top = s.pop()
                if not matches(top,symbol):
                       balanced = False
        index = index + 1
    if balanced and s.isEmpty():
        return True
    else:
        return False

def matches(open,close):
    opens = "([{"
    closers = ")]}"
    return opens.index(open) == closers.index(close)

```

## Converting Decimal to Binary
```Python
def divideBy2(decNumber):
    remstack = Stack()

    while decNumber > 0:
        rem = decNumber % 2
        remstack.push(rem)
        decNumber = decNumber // 2

    binString = ""
    while not remstack.isEmpty():
        binString = binString + str(remstack.pop())

    return binString
```

### Base Converter
```Python
def baseConverter(decNumber,base):
    digits = "0123456789ABCDEF"

    remstack = Stack()

    while decNumber > 0:
        rem = decNumber % base
        remstack.push(rem)
        decNumber = decNumber // base

    newString = ""
    while not remstack.isEmpty():
        newString = newString + digits[remstack.pop()]

    return newString

```


## Infix to Posfix or Prefix
```Python
def infixToPostfix(infixexpr):
    prec = {}
    prec["*"] = 3
    prec["/"] = 3
    prec["+"] = 2
    prec["-"] = 2
    prec["("] = 1
    opStack = Stack()
    postfixList = []
    tokenList = infixexpr.split()

    for token in tokenList:
        if token in "ABCDEFGHIJKLMNOPQRSTUVWXYZ" or token in "0123456789":
            postfixList.append(token)
        elif token == '(':
            opStack.push(token)
        elif token == ')':
            topToken = opStack.pop()
            while topToken != '(':
                postfixList.append(topToken)
                topToken = opStack.pop()
        else:
            while (not opStack.isEmpty()) and \
               (prec[opStack.peek()] >= prec[token]):
                  postfixList.append(opStack.pop())
            opStack.push(token)

    while not opStack.isEmpty():
        postfixList.append(opStack.pop())
    return " ".join(postfixList)

```
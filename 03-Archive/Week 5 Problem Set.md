---
title: Week 5 Problem Set
Created: 2023-10-26 21:15
tags:
  - college
aliases:
---

---
# Week 5 Problem Set
# Instructions

### Overview

The focus of these problems will be working with information extracted from a municipal government data feed containing bids submitted for auction of property. All materials for this assignment can be found in the workspace. The data set is provided in two comma-separated files:

eBid_Monthly_Sales.csv (larger set of 12,023 bids) eBid_Monthly_Sales_Dec.csv (smaller set of 76 bids)

This assignment is designed to explore binary search tree, so you will implement a BST to hold a collection of bids loaded from a CSV file. We provide a starter console program that uses a menu to enable testing of the hash table logic you will complete. It also allows you to pass in the path to the bids CSV file to be loaded, enabling you to try both files. In this version, the following menu is presented when the program is run:

Menu:

Load Bids Display All Bids Find Bid Remove Bid Exit Enter choice:

The BinarySearchTree.cpp program is partially completed. It contains empty methods representing the programming interface used to interact with a binary search tree. You will need to add logic to the methods to implement the necessary behavior. Here is the public API for BinarySearchTree.py that you have to complete:

```

BinarySearchTree()
insert(bid: Bid)  
remove(bidId: str)
search(bidId: str)
InOrderTraversal()  
PreOrderTraversal()
PostOrderTraversal()   
```
### Prompt

You will need to perform the following steps to complete this activity:

Task 1: Define structures for tree node and housekeeping variables.

Task 2: Implement inserting a bid into the tree.

Task 3: Implement removing a bid from the tree.

Task 4: Implement searching the tree for a bid.

Task 5: Complete the function to display all bids. (InOrder, PreOrder and PostOrder)

Note that you may be able to reuse a portion of your code from a previous assignment to save you time. Look for where you have used a Node structure to implement a linked list.

Here is sample output from running the completed program:

```Python
python3 main.py

1 Load Bids

2 Display All Bids

3 Find Bid

4 Remove Bid

9 Exit

Enter choices: 1

now loading csv file eBid_Monthly_Sales_Dec.csv...

at 1661126033.8169522: loadBids time spent: 0.0006840229034423828(sec)

Enter choices: 2
...

ID: Federal Signal Siren Amps (Emergency Provider Only), Title: 98385, Fund: Enterprise, Amount: 25.0

ID: Table, Title: 98235, Fund: General Fund, Amount: 22.01

ID: 5 Chairs, Title: 98233, Fund: General Fund, Amount: 19.0

ID: 2 Chairs, Title: 98225, Fund: General Fund, Amount: 20.0

ID: Chair, Title: 98223, Fund: General Fund, Amount: 71.88

1 Load Bids

2 Display All Bids

3 Find Bid

4 Remove Bid

9 Exit

Enter choices: 9

Bye!
```


### AddNode
```Python
if node.bid.bidId > bid.bidId:
	if not node.left:
		node.left = Node(bid)
	else:
		addNode(node.left,bid)

else:
	if not node.right:
		node.right = Node(bid)
	else:
		addNode(node.right,bid)

if self.root is None:
	self.root = Non(bid)
else:
	addNode(self.root, bid)
```
### In Order
```Python
if node is not None:
	inOrder(node.left)
	print(f'{node.bid} ->')
	InORder(node.right)
```

### Pre Order
```Python
if node is not None:
	print(f'{node.bid} ->')
	preOrder(node.left)
	preORder(node.right)
```

### Post Oder
```Python
if node is not None:
	postOrder(node.left)
	postORder(node.right)
	print(f'{node.bid} ->')
```


### Search
```Python
def searchNode(node, bidId):
	if not node:
		return None
	elif bidId == node.bid.bidId:
		return node.bid
	elif bidID < node.bid.bidId:
		return searchNode(node.left,bidId)
	else:
		return searchNode(node.right,bidId)

return SearchNode(self.root,bidId)
```


### Remove
```Python
def findMinNode(node):
	tmp = node.right
	while tmp.left
		tmp = tmp.left
	return tmp

def removeNode(node: Node, bidID: int) -> Node:

	if node is None:
		return None
	elif bidID < node.bid.bidId:
		node.left = removeNode(node.left,bidId)
	elif bidID > node.bid.bidId:
		node.right = removeNode(node.right, bidId)
	else:
		if node.left is None and node.right is None:
			node = None
		elif node.right is None:
			tmp = node
			node = node.left
			tmp = None
		elif node.left is None:
			tmp = node
			node = node.right
			tmp = None
		else:
			minNode = findMinNode(node)
			node.bid = minNode.bid
			node.right = removeNode(node.right, minNode.bid.bidId)
	return node
```
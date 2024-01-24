---
title: Functions.php
Created: 2023-12-31 14:22
tags:
  - wordpress
aliases:
---
# functions.php
- You can add custom PHP functions, classes, interfaces and more.
- This file is automatically loaded.


## Adding Actions or Filters to Hooks
- Hooks are a way for one piece of code to interact/modify another.
- There are two types of hooks [[Actions]] and [[Filters]]
	- [[Actions]] allow you to add data or change how WordPress operates. The do not return anything.
		- Echoing output to a user.
		- inserting an item into the database.
		- *an action interrupts the code flow to do something, and then returns back to the normal flow without modifying anything.*
	- [[Filters]] give the ability to change data during the execution of Wordpress Core, Plugin and themes.
		- Callback functions will accept a variable, modify it, and return it.
		- *used to modify something in a specific way so that the modification is the used by the code later on.*







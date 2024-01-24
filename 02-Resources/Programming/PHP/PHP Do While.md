---
title: PHP Do While
Created: 2024-01-13 22:01
tags:
  - php
aliases:
---
# PHP Do While
- Similar to the [[PHP While|While]] loop but will execture *once* without the conditional being checked.
	- After the first iteration it will behave like a regular [[PHP While|while]] loop.

```PHP
$count = 1;
do {
	echo "The count is: " . $count . "\n";
	$count += 1;
} while ($count < 11);
```

>[!warning] This loops requires a semicolon at the end.

>[!tip] Only use this type of loop when you always need the code block to execute at least one time.




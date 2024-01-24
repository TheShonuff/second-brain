---
title: Grid Movements
Created: 2023-12-09 13:51
tags:
  - codewars
aliases:
---

# Grid Movements
## The Goal
- Program must allow thor to reach the light of power

### Rules
- Thor moves on a map which is 40 wide by 18 high. Note that the coordinates (X and Y) start at the top left! This means the most top left cell has the coordinates "X=0, Y=0" and the bottom right has the coordinates "X=39, Y=17"
- You are given the X,Y coordinates of Thor's initial position
- You are given the X,Y coordinates of the destination.


## Solution
```Python
import sys
import math

light_x, light_y, initial_x, initial_y = [int(i) for i in input().split()]
thor_x, thor_y = initial_x, initial_y

while 1:
	remaining_turns = int(input())
	direction_x = ''
	direction_y = ''

	if thor_x > light_x:
		direction_x = 'W'
		thor_x -= 1
	elif thor_x < light_x:
		direction_x = 'E'
		thor_x += 1

	if thor_y > light_y:
		direction_y = 'N'
		thor_y -= 1
	elif thor_y < light_y
		direction_y = 'S'
		thor_y += 1
	print(direction_x + direction_y)
```



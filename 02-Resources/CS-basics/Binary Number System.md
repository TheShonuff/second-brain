---
title: Binary Number System
creation date: 2022-11-26 12:47
aliases: []
tags: reading cs
---

# Binary Number System
- Binary numbers are in Base 2 system.
	- The number is ethier a 1 or a 0
	- 1 simply means on 
	- 1 simply means off
- Typical math is done in Base 10 system. 
	- Also Known as **Deca**
	-  I.E 10,100,20,12,5 

## Converting Binary to Decimal 
- Converting a binary number to decimal is done simply by taking each integer and apply $2^n$ Working from right to left we start at zero and add 1 to the exponent. 
	- I.E 1010
	- $2^{3}$ + $2^{2}$ + $2^{1}$ + $2^{0}$  = 8 + 2 = **10**

## Converting Decimal to Binary 
There are a couple of way to convert a base 10 number to base 2. 
1. Subtract the largest possible deca number from the integer. Then add a 1 to the spot that value resides.
	-  I.E: 55
	-  55-32 = 23 then 23-16 = 7 then 7-4 = 3 then 3-2 = 1 then 1-1 = 0
	- **110111**
2. Another option is to divide the integer by 2 and add a 1 if there is a remainder.
	- 55/2 = 27.5 the 27/2 = 13.5 then 13/2 = 6.5 then 6/2 = 3 then 3/2 = 1.5 then 1/1 =1
	- The numbers are added right to left
	- The first result is the LSB and the last result is the LSB
	- **110111**




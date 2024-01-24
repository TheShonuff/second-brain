---
title: InFix, PreFix and PostFix Expressions
Created: 2023-10-01 15:51
tags:
  - algorithms
aliases:
---

---
# InFix, PreFix and PostFix Expressions

## Infix
- When the operator appears inbetween the integers.
- $B*C$
- The problem is the computer doesn't automatically assume **Order of precedence**
	- $A + B * C$ 
	- In order to guarantee there is no confusion we would **fully parenthesize** the expression.
	- $(A +(B*C))$

## Prefix
- Expression notation requires that all operators precede the two operands
- $A + B * C$ would become $+A*BC$
- $(A+B) * C$ would become $*+ABC$

## Postfix - Reverse Polish Notation
- Expression notation comesafter the corresponding operands.
- $A + B * C$ would become $ABC*+$
- $(A+B) * C$ would become $AB+C*$



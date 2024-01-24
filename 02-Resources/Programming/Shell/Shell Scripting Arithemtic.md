---
title: Shell Scripting Arithemtic
creation date: 2022-11-12 14:53
tags: shell/arithemtic filed
---

# Shell Scripting Arithemtic
Shell scripting arithemtic is a bit different.

We can set the variable then perform the arithemtic using **double parenthesis**. This is considered *Bash Arithmetic Expansion*. This should be the preferred way unless doing arithmetic in a for loop or if statement.
```bash
Division=$((10/3))
echo "$Division"
```

**Compound notation** does not use the *$* symbol

```sh
((x=2, y=3, a=x+y, b=x*y, c=x**y))
echo $a, $b, $c 
```

We can use the **Let** command
```bash
x=10
y=3

let "z = $(( x * y ))"
echo $z
```

We can use **expr** wiith *backticks*
```bash
a=10
b=3

sum=`expr $a + $b`
echo $sum
```




# Footer
### Source
- 
### Tags
- #reading


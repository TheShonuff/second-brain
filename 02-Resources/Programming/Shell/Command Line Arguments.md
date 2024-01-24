---
title: arguments
creation date: 2022-11-12 13:46
tags:
  - shell/basics
---

# Command Line Arguments

Parameters passed to a shell script from the command line. There are also know as **positional parameters**

The **bash** shell has special variables reserved to point to argurmnets which are save numerically. The first agrument would be *$1*... The second would be *$2* and so on. The special characyer $# stores the total number of arguments.

> [!note] the script file name is saved at *$0*

## Using the arguments

| Symbol    | Description                            |
| --------- | -------------------------------------- |
| $1 ... $n | Positional argument                    |
| $0        | Script name                            |
| $@        | Value of the arguments that are passed |
| $#        | Total number of arguments              |
| $*        | Get's double quoted arguments          |
| \$\$      | Know the process ID                    |
| $? or $!  | Exis status                                       |

See [[Displaying Input Examples]]

# Footer
### Source
- 
### Tags
- #reading



---
title: GetOpts
creation date: 2022-11-11 23:58
tags: shell filed
---

# GetOpts
Most unix commands accpet a number of [[Command Line Arguments]] and we can use **getopts** to parse the [[Command Line Options]] given on the command line.

```sh
grep -v '^#' .zshrc
```

Using **getopts** allows for the elimination of tricky *if* or *while* loops.

To use **getopts** we need to provide a specification describing the expected options.

```sh
while getopts "abc:" par; do
	case $par in
		(a) aopt=1;;
		(b) bopt=1;;
		(C) carg=$OPTARG;;
		(?) exit 1;;
	esac
done
shift $((OPTIND -1))
```

>[!note] There is a difference between getopt and getopts

**getopt** is a external utility. Mainly used for long options names. ie: *dir*, *env* 

**getops** is a shell builtin. It's more flexible and understands the *-* option terminator. It's also capable of parsing longer options names with *-:* style syntax.

# Footer
### Source
- Udemy - Linux Shell Scripting
### Tags
- #reading

## getops alternative
An option that works on multiple shells [script wiith options](https://gist.github.com/dgoguerra/9206418) 
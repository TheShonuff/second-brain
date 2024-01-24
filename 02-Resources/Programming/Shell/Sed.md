---
title: Sed
creation date: 2022-11-19 21:29
aliases: []
tags: reading shell filed 
---

# Sed
 - Performs text transformations on streams. Think of it as the command line version of **find and replace**. Examples include:
	 - Substitute some text for other text
	 - Remove lines
	 - Append text after given lines
	 - Insert text before certain lines

> [!note] Sed is used programmatically not interactively

The format of a sed s pattern is 
```sh
sed 's/search-pattern/replacement-string/flags'
```

By default sed only replaces the first occurance. Use the **g** for a *global replace*

To save the changes to a new file use **>** to send to a new file.

The first character that follows the **'s'** is the delimiter.

```sh
echo 'home/jason' | sed 's#/home/jason#/export/users/jasonc#'
# /export/users/jasonc
That Same as
echo '/home/jason' | sed 's/\/home\/jason/\/export\/users\/jasonc/'
prints /export/users/jasonc
```


Supplying a number before the expression will specify which line the **find and replace** will happen.

Supplying a regex before the sed regex with specify that the **find and replace** will only occur on lines containing what matches the intial regex.

# Footer
### Source
- 



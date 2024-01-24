---
tags:
  - python
---

# Python Writing Files
- To write to a file to store data use `file.write()` method.
	- The method only accepts a string argument. Integers and floating-point values must be converted using `str()`
- When writing to a file the mode must be explicitly set.
	- **r** - open file for reading.
	- **w** - open file for writing.
	- **a** - open file for appending.

>[!tip] A `+` can be added to the end of the mode to specify an **update mode** which allows both reading and writing 


## Output buffer
- Output to file is buffered by the interpreter before being written to the hard disk. 
- By default, data is line-buffered.
	- Data is only written to disk when a newline character is output.
- The buffer size can be toggled with the optional buffering argument to the `opend()` function.
	- A value > 1 sets a specific buffer size in bytes
	- A 0 disables the buggering.
- The `flush()` method can be called to force the interpreter to flush the output buffer to disk.


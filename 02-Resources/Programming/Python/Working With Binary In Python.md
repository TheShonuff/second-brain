---
tags:
  - python
---
# Working With Binary In Python
- A **bytes object** is used to represent a sequence of single byte values.
- **Byte objects** are immutable.
- Created using the `bytes()` built-in function
	- `bytes('A text string', 'ascii')` creates a sequence of bytes by encoding the string as ASCII
	- `bytes(100)` creates a sequence of 100 bytes whoe values are all 0
	- `bytes([12,15,20])` creates a sequence of 3 bytes with values from a list.

>[!tip] Alternatively, a programmer can write a bytes literal, similar to a string literal, by prepending a `b` prior to the opening quote

```Python
my_bytes = b'this is a bytes literal'

print(my_bytes)
print(type(my_bytes))
```

- We can specify raw byte values in a string or bytes literal using the \x escape character preceding the hexadecimal value that describes the value of the byte. 

```Python
print(b'123456789 is the same as \x31\x32\x33\x34\x35\x36\x37\x38\x39')
```
>[!note] The raw bytes values 0x31 through 0x39 are automatically converted to the corresponding ASCII encoded values

- We can also access files using **binary file mode** by adding a `'b'` character to the end of the mode string in a call to `open()` when [[Python Reading Files|opening files]]. 
	- `open('myfile.txt', 'rb')`

>[!tip] When a file is opened using a binary mode, the file.read() method returns a bytes object instead of a string. Also, the file.write() method expects a bytes argument.


## The Struct Module
- Commonly used standard library module for packing values into sequences of bytes and unpacking sequences of bytes into values(like integers and strings). 
- The `struct.pack()` function packs values such a strings and integers into sequences of bytes.
	- The first argument describes how the following arguments should be converted into bytes.
	- The `<` character indicates the **byte-order**, or **endianness**, of the conversion.
		- Which determines the most significant or least significant byte is placed in first in the byte sequence.
			- **h** describes the values as a 2-byte integer
			- **b** describes the values as a 1-byte integer
			- **l** describes the values as a 4-byte integer
			- **s** describes the values as a string

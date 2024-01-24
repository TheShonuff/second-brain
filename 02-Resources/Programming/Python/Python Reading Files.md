---
tags:
  - python
---

# Python Reading Files
- A common programming task of reading files can be accomplished using the built-in `open()` function
- Requires a single argument that specifices the path to the file.
- the `file.close()` method closes the file.
	- No more read or writes are able to occur afterwards.
- `file.read()` method returns the file contents as a string.
- `file.readlines()` method returns a list of strings.
	- The first element is the contents of the first line.
	- The second element is the contents of the second line.
- Both `file.read()` and `file.readlines()` can be given an optional argument that specifies the number of bytes to read from the file. 
	- Each method will stop reading when the end-of-file **EOF** is detected.

```Python
my_file = open('readme.txt')
lines = my_file.readlines()
print(lines[1])
```
>[!note] Opens reads lines from 'readme.txt' and then outputs the second line


## The 'with' Statement
- Can be used to open a file, execute a block of statements and automatically close the file when complete.
- Recommended when opening files becasue closure of file is guaranteed.
```Python
import csv
row1 = ['100', '50', '29']
row2 = ['76', '32', '330']

with open('gradeswr.csv', 'w') as csvfile:
	grades_writer = csv.writer(csvfile)
	grades_writer = csv.writerow(row1)
	grades_writer = csv.writerow(row2)

	grade_writer.writerows([row1, row2])
```


## DictReader
```Python
import csv

with open('names.csv', newline='') as csvfile:
    reader = csv.DictReader(csvfile)
    for row in reader:
        print(row['first_name'], row['last_name'])

Eric Idle
John Cleese

print(row)
```
---
tags:
  - python
---

# Python Data Library
- This doucment will serve as a basis of reading and writing data file with python

## CSV
```Python
import csv
```

- To read a CSV file in use <code>csv.reader()</code>
## Syntax
```Python
csv.reader(csvfile, dialect='excel', **optional_parameters)
```
- Some custom parameters include
	- specifying the delimiter. <code>delimiter = </code>
	- Some files have a space after the value <code>skipinitialspace =</code>
	- Some files have quotes <code>quoting=csv.QUOTE_ALL</code>
		- specifies that all values are in quotation marks
		- <code>csv.QUOTE_MINIMAL</code> quotes around special characters
		- <code>csv.QUOTE_NONNUMERIC</code> quotes around non-numeric values
		- <code>csv.QUOTE_NONE</code> No entires have quotes
- To specify a dialect <code>csv.register_dialect( )</code>
	- We can we can name a pass paramters here to specify only once every time the csv is read or written.
	
### Example
```Python
with open('text.csv', 'r') as file:
	reader = csv.reader(file)
	for row in reader:
		print(row)
```
>[!note] Will print each row in a csv file

## Sniffer
- We can deduce the format of a csv with <code>Sniffer</code>
- The <code>Sniffer</code> has two methods
	- <code>sniff(sample, delimiter=None)</code> This function analyses a given sample of the csv and returns a dialect.
### Example
```Python
import csv
with open('text.csv', 'r') as csvfile:
	sample = csvfile.read(64)
	has_header = csv.Sniffer().has_header(Sample)
	print(has_header)

	deduced_dialect = csv.Sniffer().sniff(sample)

with open('text.csv', 'r') as csvfile:
	reader = csv.reader(csvfile, dedced_dialect)

	for row in reader:
		print(row)
```


```Python
import csv
filename = input()
dict = {}
with open(filename) as file:
	reader = csv.reader(file)
	data = list(reader)
```
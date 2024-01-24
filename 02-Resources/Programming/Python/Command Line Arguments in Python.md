---
tags:
  - python
  - shell
---
# Command Line Arguments in Python
- Vocabulary in this section:
	- **Command**: Program or routine
	- [[Command Line Arguments|Arguments]]: A piece of information the command uses to perform actions
	- [[Command Line Options|Options]]: An optional argument that modifies a command behavior
	- **Parameter**: An arugment the option uses to perform its intended operation
	- **Subcommand**: A predefined name that can be passed to an application to run a specific action.

```Shell
pip install -r requirments.txt
```
In this example the collow CLI components are used:
- **pip**: The command's name
- **install**: The subcommand
- **-r**: An option of the install subcommand
- **requirments.txt**: An argument, specifically a parameter of the -r option

---
# argparse
- [Documentation](https://docs.python.org/3/library/argparse.html#module-argparse)
- Python's <code>argparse</code> module allows:
	- Parse command-line **arugments** and **options**
	- Take a **variable number of parameteres** in a single option
	- Provide **subcommands** in your CLI's
>[!tip] Automatically checks the presence of arguments

### Example
```Python
import argparse

parser = argparse.ArgumentParser(
								 prog='Program Name'
								 description='What the program does'
								 epilog='Text at the bottom of help')
parser.parse_args()
```
> [!note basic setup of argpase]


## Adding an Argument
- The <code>argparse.ArgumentParser()</code> method attches individual specifications to the parser.

```Python
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('filename')
parser.add_argument('-c', '--count')
parser.add_argument("-o", "--Output", help = "Show Output")
parser.parse_args()

If args.Output:
	print("Displaying Output as: % s" % args.Output)
```
>[! note] Adding arguments

## Actions
```Python
parser.add_argument('--foo', action='store_true')
parser.add_argument('--bar', action='store_false')
parser.add_argument('--baz', action='store_false')
```

- The <code>ArgumentParser.parse_args()</code> method runs the parser and places the extracted data in a <code>argparse.Namespace</code> object.

```Python
args = parser.parse_args()
print(args.filename, args.counts)
```
>[!note] Parse arguments


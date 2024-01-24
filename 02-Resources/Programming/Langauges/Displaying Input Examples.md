---
tags: shell/basics filed
---
# Displaying Input Examples

## Variables
Assigning a variable
```sh
VARIABLE='This is a value'
```
Assigning a variable from a command
```sh
PASSWORD=${date +%s}
```
It's good practice to use *local* a shell builtin to declare local variables to the function.

## Input
```sh
read -p 'Enter Something: ' SOMETHING_VARIABLE
```

### Display Input
```sh
echo "You executed this command: ${0}"
```
```sh
echo "You used $(dirname ${0}) as the path to the ($basename ${0}) script"
```
```sh
NUMBER_OF_PARAMETERS="${#}"
echo "You supplied ${NUMBER_OF_PARAMETERS} argument(s) on the command line"
```
```sh
echo "Parameter 1: ${1}"
echo "Parameter 2: ${2}"
echo "Parameter 3: ${3}"

# loop through positional paramters
while [[ "${#}" -gt 0 ]]
do 
	echo "Number of parameters: ${#}"
	echo "Parameter 1: ${1}"
	echo "Parameter 2: ${2}"
	echo "Parameter 3: ${3}"
	echo
	shift
done
```

### Positional Parameters
List all command line parameters in a single string format
```sh
echo "All (*) args are" $*
```
List all command line parameters in a array format
```sh
echo "Array of args are" $@
```
Numeric count of all command line arguments
```sh
echo "Number of args. (#) are" $#
```

## Redirection
Redirect STDOUT to a file *>*
```sh
FILE="tmp/data"
head -n1 /etc/passwd > ${FILE}
```
Redirect STDIN to a program *<*
```sh
read LINE < ${FILE}
echo "line contains: ${LINE}"
```
Redirect STDOUT to a file, appeding the file *>>*
```sh
echo "${RANDOM} ${RANDOM}" >> ${FILE}
```
Redirect STDERR to a file using  *2>*
```sh
ERR_FILe="/tmp/data.err"
head -n3 /etc/passwd /fakefile 2> ${ERR_FILE}
```
Redirect STDOUT AND STDERR to a file *&>*
```sh
head -n3 /etc/passwd /fakefile $> ${FILE}
```
Discard STDOUT
```sh
head -n3 /etc/passwd /fakefile > /dev/null
```
Discard STDERR
```sh
head -n3 /etc/passwd /fakefile 2> /dev/null
```
Discard both STDOUT and STDERR
```sh
head -n3 /etc/passwd /fakefile &> /dev/null
```

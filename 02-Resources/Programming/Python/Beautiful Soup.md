---
title: Beautiful Soup
Created: 2023-12-13 22:24
tags:
  - python
aliases:
---
# Beautiful Soup
- A html [[HTTP Requests]] needs to be made to get the content of a website

```Python
import requests

webpage = requests.get('https://www.codecademy.com/articles/http-requests')
print(webpage.text)
```


## The Object
- Makes traversing a HTML tree easy and pull relevant parts.
```Python
from bs4 import BeautifulSoup
```

- The library has several types of parsers.
	- The `html.parser` is the most popular choice.

```Python
webpage = requests.get('http://rainbow.com/rainbow.html')
soup = BeautifulSoup(webpage.content, 'html.parser')
```

## Types
- Breaks HTML pages into several types of objects

### Tags
- Corresponding to different HTML tags
- Accessing a tag from BeautifulSoup objects will get the first tag.
```Python
soup = BeautifulSoup('<div id="example">An example div</div><p>An example p tag</p>')
print(soup.div)

print(soup.div.name)
print(soup.div.attrs)
```

- **Children** of tags can be retrieved using the `.children` attribute.
```Python
for child in soup.ul.children:
	print(child)
```

- **Parents** can be accessed using the `.parents` attribute
```Python
for parent in soup.li.parents:
	print(parent)
```
#### NavigableStrings
- Are pieces of text that are in the HTML tags on the page.
- Can be retrieved from inside a tag by calling `.string`
```Python
print(soup.div.string)
```


## Find
- There are two methods for 'finding' elements on a webpage
	- `.find()` - Returns the first tag that matches the parameter
	- `.find_all()` - finds all the occurrences of a tag and returns a list.
- These methods can be combined with regex, attributes or functions to have a lot of control over selecting elements.
### Regex
- A great method for finding tags on a webpage.
```Python
import re
soup.find_all(re.compile('[ou]l'))
```
>[!note] match either o or u and l. If we want to select every `<ol>` or `<ul>` tag.
### Using Lists
```Python
soup.find_all(['h1', 'a', 'p'])
```

### Using Attributes
- Match elements with relevant attributes.
- Pass a dictionary of attributes as a parameter to `find_all`
```Python
soup.find_all(attrs=('class':'banner'))
```
>[!note] All elements with the *banner* class

### Using A Function
- A function can be passed into the `.find_all`.

```Python
def has_banner_class_and_hello_world(tag):
	return tag.attr('class') == 'banner' and tag.string == 'hello world'

soup.find_all(has_banner_class_and_hello_world)
```


## Select for CSS Selectors
- The `.select` method will take in all of the CSS selectors you normally use in a .css file.
```Python
soup.select('.class')
soup.select('#id')
```

## Reading Text
- The `.get_text()` to retrieve text inside the tag.
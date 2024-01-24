---
tags:
  - python
---

# Python Dates
- use the **datetime** module to manipulate dates and times

```Python
import datetime
```


## Formatting
- The <code>strftime()</code> method is defined under classes <code>date</code>,<code>datetime</code> and <code>time</code>. The method creates a formatted string from a given  <code>date</code>,<code>datetime</code> and <code>time</code> object.
- [Strftime](https://www.programiz.com/python-programming/datetime/strftime)

```Python
from datetime import datetime

now = datetime.now()
s1 = now.strftime("%m/%d/%Y, %H:%M:%S")
```



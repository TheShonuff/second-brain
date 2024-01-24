---
title: Finally
Created: 2023-10-18 22:21
tags:
  - python
aliases:
---
# Finally
- A variation on the [[Try & Except]] 
- Executes code regardless if an exception has been raised.

![[Pasted image 20231018222149 1.png]]

```Python
try:
	check_password()
except ValueError:
	print('Wrong Password! Try again')
else:
	login_user()
finally:
	load_footer()
```
>[!note] The footer would be loaded regardless if the user was able to login

```Python
try: 
	check_password()
except:
	load_footer()
```
>[!note] can be used without an else or except clause


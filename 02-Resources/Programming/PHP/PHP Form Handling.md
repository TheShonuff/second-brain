---
title: PHP Form Handling
Created: 2024-01-15 21:11
tags:
  - php
aliases:
---
# PHP Form Handling
- PHP provides the capability of handling form input from users through HTML forms.


## Superglobals
- The list of superglobals
	- `$GLOBALS`
	- `$_SERVER`
	- `$_GET` Contains an associative array of variables passed using the query parameters in the url
	- `$_POST` Contains an associative array of variables using a form submitted using the "POST" method.
	- `$_FILES`
	- `$_COOKIE`
	- `$_SESSION`
	- `$_REQUEST` - Contains `$_GET`, `$_POST`, and `$_COOKIE`
	- `$_ENV`
## GET Form Handling
- Setting a form's method to **GET** specifies that you would like the form to be submitted using the **GET** method.
	- Form entries are passed using the *URL*
>[!tip] The default behavior of any form is **GET**

- Values are accessed from the associative array using the input value `name`

```HTML
<form method="get">
First name: <input type="text" name="first">
<br>
Last name: <input type="text" name="last">
<br>
<input type="submit" value="Submit Name">
</form>
```
>[!note] The value for `first` would be accessed using `$_GET['first']`

## Post Form Handling
- The data is sent using the headers of the HTTP request instead of the url.
- Values are accessed similar to how values are accessed in `$_GET` forms.
	- Accessed using `$_POST['value']`

## Action Attribute
- What "action" will be performed after the form is submitted.
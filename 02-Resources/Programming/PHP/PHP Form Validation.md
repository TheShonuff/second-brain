---
id: PHP Form Validation
aliases:
  - PHP Form Validation
tags:
  - php
Created: 2024-01-15 21:56
title: PHP Form Validation
---

# PHP Form Validation

- The first step for validation is **client-side validation**. Where inputs are validated onthe client side, html.

  - Form inputs can expect certain ranges of integers or strings.
  - Form inputs can expect a string to match a particular pattern.
  - The `required` tag will indicate that an input must be present to be accepted.

- The second step for validation shoud be **back-end validation** where the inputs are validated on the server.

  - There are several advantages
    - Enables validation code with more computational power
    - Allows validation code that a user can't see. Malicious users can't see how the inputs are validated.
    - Inputs can be validated against other data.

- There are two main ways to validate inputs on the _server-side_.
  - Takes place while the user is still inputting data into the form. Asynchronous requests to the server with peices of the data.
  - Takes place after the form has been submitted.

> [!tip] Backend validation should never trust the data the it receives

## Simple Validation

```PHP
<?php
$validation_error = "";
$user_language = "";

if ($_SERVER["REQUEST_METHOD"] === "POST") {
$user_language = $_POST["language"];
  if ($user_language != "PHP") {
    $validation_error = "* Your favorite language must be PHP!";
  }
}
?>

<form method="post" action="">
Your Favorite Programming Language: <input type="text" name="language" value="<?php echo $user_language;?>">
<p class="error"><?= $validation_error;?></p>
<input type="submit" value="Submit Language">
</form>
```

## Basic Data Sanitizing

- PHP provides a few built-in functions to help
  - `trim()` Remove any whitespace from characters from the beginning or end of a string.
  - `htmlspecialchars()` Transforms HTML elements into HTML entities. Characters that represent HTML elements but do not display as HTML.
  - `filter_var()` Operates on a variable and passes it through a "filter" that produces a desired outcome.
    - Takes two arguments
      - The data to be sanitized
      - The type of sanitation
    - [Full list of sanitation methods](https://www.php.net/manual/en/filter.filters.sanitize)
    - Can also be used to **validate** form inputes. [full list of validation methods](https://www.php.net/manual/en/filter.filters.validate.php)
      - If the variable is deemed valid, it will be returned.
        - otherwise it will return `FALSE`
    - There is an optional third argument.
      - Takes an assocaited array `["options => ["min_range" => int, "max_range" => int]]`

## Custom Validation

- When the validations offered by `filter_var()` are not enough. We have to roll our own functions that validate form input.
- A common method is to compare the input to a pattern using `preg_match()`.
- `preg_match()` - takes two arguments
  - a pattern string with a regular expression.
  - a subject string to check.
  - Returns `1` if a match is found. Returns a `0` if no match is found
- `strlen()` - used to check the length of a given input.

## Sanitizing for Back-end Storage

- all data needs to be sanitized before storing in a database.
- `preg_replace()` is used to sanitize data.
  - takes a regular expression and some replacement text.


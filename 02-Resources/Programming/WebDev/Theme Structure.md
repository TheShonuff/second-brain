---
title: Theme Structure
Created: 2023-12-31 13:56
tags:
  - wordpress
  - webdev
aliases:
---
# Theme Structure
- Themes are nothing more than a collection of various files that rely on different web technologies.

## Basic Theme Structure
- **parts**
	- footer.html
	- header.html
- **Patterns**
	- example.php
- **styles**
	- example.json
- **templates**
	- 404.html
	- archive.html
	- index.html
	- singular.html
- README.txt
- functions.php
- screenshot.png
- style.css
- theme.json

### Required Files
- `style.css`- Required for configuring theme data, such as name and description.
- `templates/index.html` - The fallback template. necessary for all block themes.

### Standard Folders
- `parts` - Houses custom template parts for the theme.
	- headers, footers, sidebars
- `patterns` - Reussable paaterns mode up of one or more blocks that users can insert via the editor interface.
- `styles` - Variations on the theme's global settings and styles stored in JSON files.
- `templates` - Files that represent the overall document structure of the front-end. Templates are made up of block markup and are what site visitors see.

## Advanced Theme Structure
- **assets**
	- *css*
		- core-site-title.css
	- *images*
		- header-background.png
	- *js*
		- navigation.js
- **inc**
	- ClassName.php
	- functions-helpers.php
- **parts**
	- footer.html
	- header.html
- **patterns**
	- example.php
- **styles**
	- example.json
- **templates**
	- 404.html
	- archive.html
	- index.html
	- singular.html
- .editorconfig
- .gitattributes
- README.txt
- functions.php
- package.json
- screenshot.png
- style.css
- theme.json
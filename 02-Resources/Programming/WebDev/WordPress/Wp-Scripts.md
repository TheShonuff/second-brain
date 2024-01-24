---
title: Wp-Scripts
Created: 2024-01-14 14:17
tags:
  - wordpress
aliases:
---
# Wp-Scripts
- [W-Scripts Documentation](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts/)
- The `@wordpress/scripts` package is a set of configuration files and scripts to simplify the development process.
- *wp-scripts* can do the following
	- **Compilation** - Converts moden javascript into code compatible using babel
	- **Bundling** - Uses webpack to combine multiple JavaScript files into a single bundle
	- **Code Linting** - Provides configurations for ESLint to help ensure code quality
	- **Code Formatting** - Incorporate Prettier for automated code sytling
	- **Sass Compilation** - Convers Sass files into standard CSS
	- **Code Minification** - Reduces the size of the JavaScript code for production.


## Installation
- There's a recommended approach to setting up a project.
- Create a project folder that contains
	- `package.json`
	- `build/`
	- `src/`
- Run `npm init`
	- The *entry point* is `build/index.js`

- Project Folder/
	- build/
	- node modules/
	- src/
		- index.js
	- package-lock.json
	- package.json




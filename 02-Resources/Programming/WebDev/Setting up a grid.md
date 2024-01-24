---
title: Setting up a grid
creation date: 2022-11-05 23:16
tags:
  - web
  - html/grid
  - webdev
---
# Setting up a grid
A [[Grid|grid]] is setup using [[div]]'s that seperate elements from rows and columns. 
```html
<div class="row">
	<div class="column1"></div>
	<div class="column2"></div>
</div>
```

More elaborate layouts have columns that contain rows.
```html
<div class="row">
	<div class="column1">
		<div class="row">
			<div class="column1a"></div>
			<div class="column1b"></div>
		</div>
		<div class="row">
			<div class="column1c"></div>
			<div class="column1d"></div>
		</div>
	</div>
	<div class="column2"></div>
</div>
```

It's common in grid layouts to give the columns class names indicating their width. 

```html
<div class="row">
	<div class="col-2-3">
		<div class="row">
			<div class="col-1-4"></div>
			<div class="col-1-4"></div>
			<div class="col-1-2"></div>
		</div>
		<div class="row">
			<div class="col-1-1"></div>
		</div>
	</div>
	<div class="col-1-3"></div>
</div>

```

>[!note]
>**col-1-4** would indicate a *25%* or *1/4* width. **col-2-3** would indicate a *67%* or *2/3* width.

# Footer
### Source
- 
### Tags
- #reading



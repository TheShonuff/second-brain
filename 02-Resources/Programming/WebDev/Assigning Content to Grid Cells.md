---
title: Assigning Content to Grid Cells
creation date: 2022-11-06 00:23
tags:
  - filed
  - css/grid
  - webdev
---

# Assigning Content to Grid Cells

You can place a specific element within a grid cell at the intersection of a specified row and column. By default all specified elements are placed in the grid cell located at the intersection of the first row and first column. To place elements elsewhere

```css
grid-row-start: integer;
grid-row-end: integer;
grid-column-start: integer;
grid-column-end: integer;
```

The **integer** specifies the starting and ending row or column.

The following rule sets the aside element to cover the second and third rows and the first and second columns

```css
aside {
	grid-row-start: 2;
	grid-row-end: 3;
	grid-column-start: 1;
	grid-column-end: 2;
}
```

We can also use a more compact form. 

```css
aside {
	grid-row: 2/3;
	grid-column: 1/2;
}
```

You can also just provide a single row and column

```css
aside {
	grid-row: 2;
	grid-column: 1;
}
```

# Footer
### Source
- HTML and CSS
### Tags
- #reading



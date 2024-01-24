---
title: Defining a CSS Grid
creation date: 2022-11-06 00:05
tags: css/grid web filed
---

# Defining a CSS Grid

Defining a grid system with HTML addes a lot of bloat and blocks to the markup. Grids can be defined in the CSS.
```css
selector {
	display: grid;
	grid-template-rows: track-list;
	grid-template-columns: track-list;
}
```
The **Display:** *grid* establishes the selected elements will be a *grid*. **grid-template-rows** and **grid-template-columns** sets the *rows* and *columns*. 

The following block sets 3 rows with the *height* of the first row at 100px, next row to automaticaly size to the content and the last row is 100px. The style sets the first and last columns *width* to 25% and the middle column to 50%.

```css
section {
	display: grid;
	grid-template-rows: 100px auto 100px;
	grid-template-columns: 25% 50% 25%;
}
```

CSS gride styles introduces **fr** unit, which represents the fraciton of available space left on the grid *after* all the rows or columns have attained their maximum allowable size. The following style sets two columns that are 200px and 250px wide and then two columns that are 1fr and 2fr.

```css
grid-template-columns: 200px 250px 1fr 2fr;
```

The total allowable space is 450px. Whatever space remains is divided between the last two columns. 1fr or 1/3 alloted to the third column and 2/3 for the fourth column.

> [!note] 
> Think the **fr** unit as a *share* of the available space.

[[Assigning Content to Grid Cells]]

# Footer
### Source
- HTML and CSS
### Tags
- #reading


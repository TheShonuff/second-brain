---
tags:
  - python
---
# Tk Geometry Management
- Relies on the concept of master and slave widgets.
- The **grid** geometry manager is what's commonly used.
- [[Tk Widgets|Widgets]] are assigned a *column* number and a *row* number.
	- This indicate each widgets position relative to other widgets.
	- Widgets in the same column are above or below each other.
	- Widgets in the same row are to left or right of each other.

## Layout within the Cell
- The width of a column and height of the row depends on all the widgets they contain.
- By default, if a cell is larger than the widget it contains, the widget will be centered.
- The <code>sticky</code> option changes default behavior.
	- Its a value, a string of 0 or more compass directions **n,s,e,w**
	- These specify which edge the widget should be "stuck" to.
	- A *north* option will stick the widget to the top of the cell.
	- A *west* option sticks to the left of the cell
	- *nsew* will stick to every side.

## Handling Resize
- Every column and row in the grid has a **weight** option.
	- This tells the grid how much the column or row should grow.
	- By default each column weight is zero.
- To resize a positive weight needs to be assigned to at least one column and one row.
	- The weight is relative.
	- If two columns have the same weight, they'll expand at the same rate.
- Grid has two methods.
	- <code>columnconfigure</code>
	- <code>rowconfigure</code> 
>[!tip] <code>columnconfigure</code> and <code>rowconfigure</code> takes a <code>minsize</code> option to specify a minimum size

## Padding
- Frames have <code>padding</code> options.
- Frames are typically used as master to host slave widgets like buttons.
- <code>padx</code> and <code>pady</code> can be applied directly to a widget.


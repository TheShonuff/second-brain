---
tags:
  - python
---
# Tk Widgets
- All things that are on the screen. 
- Refered to as *controls*
	- Sometimes refered to as *windows*
- Widgets are objects.
- All widgets are part of a widget hierarchy, with a single root at the top.
	- It's common to call this the **root**
>[!tip] When instantiating a widget, you must pass its parent as a parameter to the widget class. The only exception is the "root" window

```Python
root = Tk()
content = ttk.Frame(root)
button = ttk.Button(content)
```

## Configuration Options
- All widgets have several configuration options that control how the widget is displayed or behaves.
- To get a description of options ask the REPL to describe.
```Python
button = ttk.Button(root, text="Hell", command="buttonpressed")
button.configure()
```

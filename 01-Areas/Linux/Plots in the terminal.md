---
title: Plots in the terminal
Created: 2023-12-23 22:34
tags:
  - matplotlib
  - shell
aliases:
---
# Plots in the terminal
- Plots can be viewed in the terminal in a few ways

```Python
import matplotlib as mpl
import matplotlib.pyplot as plt
```
## Calling subprocess
- Using the ability of kitty to display images.
- Save the figure to a file 
	- immediately call a process in the script to display the image.
```Python
import subprocess

plt.figure(figsize=(x,y))
plt.savefig('image_to_display.png')

subprocess.call(['kitty', '+kitten', 'icat', '--align', 'left', 'image_to_display.png'])

```


## Matplolib-backend-kitty
- [Module](https://github.com/jktr/matplotlib-backend-kitty) to display plots in a kitty terminal.
- `pip insall maplotlib-backend-kitty`
	- can enable in python script
		- `matplotlib.use('module://matplotlib-backend-kitty')`
	- Or enable through enviroment variable
		- `export MPLBACKEND='module://matplotlib-backend-kitty'`

```Python
import matplotlib
matplotlib.use('module://matplotlib-backend-kitty')
from matplotlib import pyplot as plt
```

### Resizing
- by default figures are resized to the size of your terminal by default.
- Manual adjustment can be set using the `MPLBACKEND_KITTY_SIZING` enviroment vairable to manual.


## Ipython
- Python files can be loaded into the REPL using `%load <filename>`
- 
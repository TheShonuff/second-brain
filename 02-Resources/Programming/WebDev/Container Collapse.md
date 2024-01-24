---
title: Container Collapse
creation date: 2022-11-01 01:41
tags:
  - filed
  - css
  - webdev
---

# Container Collapse
Created: [[11-02-2022]]
- When every element in a container is floated, there is no content left. As far as the browser is concerned the container is empty. Therefore there is no height and no background.
- To prevent container collapse use **container**::*after*
```css
container::after {
	clear:both;
	content: "";
	display: table;
}
```


# Footer
### Source
- HTML and CSS Textbook
### Tags
- #web #css #container-collapse #container #layout
#### Links
- 

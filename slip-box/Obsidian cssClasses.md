---
title: Obsidian cssClasses
creation date: 2022-11-20 13:43
aliases: []
tags: reading obsidian note-taking
---

# Obsidian cssClasses
Putting css class information in the YAML will tell that note to load the css class from the css file. 

```css
===
cssclass: testclass
---

.markdown-preview-view.testclass {
	background-image: url("test.png");
	background-position: center center;
	background-size: 100$
}

```

The YAML will activate the testclass written in the theme file and apply that to the note that invoked the css class. 

# Footer
### Source
- 



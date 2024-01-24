---
tags:
  - projects/foh
  - webdev
---

---
Created: [[08-21-2023]]
tags: 
---
# Full Page Background

## Css-only Technique 1
```css
img.bg { 
	/* Set rules to fill background */ 
	min-height: 100%; 
	min-width: 1024px; 
	/* Set up proportionate scaling */ 
	width: 100%; 
	height: auto; 
	/* Set up positioning */ 
	position: fixed; 
	top: 0; 
	left: 0; 
} 
@media screen and (max-width: 1024px) { /* Specific to this particular image */ 
	img.bg { 
		left: 50%; 
		margin-left: -512px; 
		/* 50% */ 
	} 
}
```

## CSS-only Technique 2
```css
.bg {
	position: fixed;
	top:0;
	left: 0;

	min-width: 100%;
	min-height: 100%;
}
```




---
title: Background Styles
creation date: 2022-11-19 01:09
aliases: 
tags:
  - css
  - html
  - webdev
---

# Background Styles
There are a variety of ways to style background images with a div or element.

```css
background-image: url(url)
```

The default behavior is to place the image in the top left corner of the container and repeat the image in both vertical and horizontal direction until the image has filled the container.

We can turn off the tling or control the behavior with 

```css
background-repeat: type
```

Where type can be **repeat-x, repeat-y, no-repeat, round, space** 

The background image is attached to its container. If you scroll this may affect how the background image looks. we can use the following to adjust how that works.

```css
background-attachment: type;
```

Where type can be **scroll, fixed, local**. 

> [!note] **scroll** is the default 

Fixed background are handy to create watermarks.

## Background Position
A stated the default location is the *top-left corner*. We can change that using background-position. 

```css
background-position: horizontal veritcal
```

The first value will define the horizontal while the second will define the vertical. We can use percentages, pixels or keywords

```css
background-position: right bottom;
background-position: 30% 90%;
backgroudn-position: 30px
```

## Defining Extent
Every block element follows the [[Content Box Model]] however the background image by default only extends through the padding space and not include the margin. We can change this behavior with 
```css
background-clip: type;
```

Where type can be:
1. **content-box**: to extend the content only through the content
2. **padding-box**: to extend the content through the padding space
3. **border-box**: to extend the content through the border space. 

## Sizing and Clipping
The size of the background image is equal to the size stored in the image file. To specify a different size use:
```css
background-size: width height
```

We can also use **auto, cover, contain** with pixel dimensions. 



# Footer
### Source
- 



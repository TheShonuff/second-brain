---
id: 1707629433-react-components
aliases:
  - React Components
tags: []
---

# React Components
There are two built-in react libraries that are heavily used.
```js
import React from 'react'
import ReactDom from 'react-dom/client'
```
Since the inception of React Hooks *function components* are the standard way to create components.

A *function component* name must start with a capital. This has to do with how JSX tags are compiled. Capitalization indicates that it is a React component rather than a HTML tag.

## Return
A *function component* essentially defines factory that will build the appropriate combination of elements every time we reference it.

## Importing And Exporting
Functions are exported using `export` declaration.
```js
export default MyComponent
```

## using and Rendering a Component
HTML-like syntax can be use `<MyComponent />` 

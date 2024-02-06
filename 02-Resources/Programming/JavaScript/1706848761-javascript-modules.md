---
id: 1706848761-javascript-modules
aliases:
  - JavaScript Modules
tags: []
---

# JavaScript Modules
Modules are simply reusable pieces of code.


## Named Export Syntax
Functions can be exported from a file using the `export` keyword. Using this syntax, the name of each exported resource is in `{}`.

```js
// At the end of a file
export  {resourceToExport, anotherResource}

// exporting individual values
export const functionToExport = (element) => {something}
```

## Importing
The ES6 syntax for importing named resources is similar to the `export` syntax.
```js
import {exportedResource, anotherResource} from './path/to/module.js'
//renaming imports
import {exportedResource as newResource} from './path/to/module.js'
```

## Default Exports and Imports
A single exported value that represents the entire module. The importing and exporting of `default` is slightly different, it doesn't use `{}`.

>[!note] You'll need to group all the functions and variables into an object and default export the object for this to work.

```js
//exporting the resource
const resources = {
    valueA,
    valueB
}
export default resources

//import the resource
import importedResource from 'module.js'
```
>[!note] if the `default` export is an object, the values inside cannot be extracted until after the object is imported.

---
id: 1707074963-javascript-babel
aliases:
  - javascript babel
tags: []
---

# javascript babel


## Configuration Basic
The `.babelrc` will configure how the transpilation functions

```json
{
   "presets": [
        "@babel/preset-env"
    ]
}
```

### NPM Configuration
The `package.json` file will need a build script that performs the transpilation.
```json
{
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "build": "babel src -d out"
    }
}
```




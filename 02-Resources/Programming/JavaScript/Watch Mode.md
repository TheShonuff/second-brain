---
title: Watch Mode
creation date: 2022-12-03 00:38
aliases: []
tags: reading ts
---

# Watch Mode
watches for changes in a file to recompile
```sh
tsc <file name> --watch
```

## Multiple Files
Everything in the folder will be initalized with a tsconfig.json file. This essentially is an options file.
```
tsc --init
```
This can be combined with watch mode to recompile **all** the files.

## Managing Files
We can include and exclude files to watched by the TypeScript compiler. After the options we can add some additional options. A popular "exclude" is the node_modules however it is defaulted as an option. If "include" is set then **every** that needs to be included needs to be set.
```json
},
	"exclude": [
		"node_modules"
	]
}
```

## Setting a Compilation Target
"compilerOptions" control how the files are compiled.


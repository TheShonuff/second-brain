---
tags:
  - webdev
  - svelte
---
# Svelte
- [[Assest Handling]]
- Starting a svelte project
```shell
npm create svelte@latest <app-name>
cd <app-name>
npm install
npm run dev -- --open
```


## Svelte on Netlify
- install adapter with `npm i -D @sveltejs/adapter-netlify`
- Then add the following to `svelte.config.js`

```javascript
import adapter from '@sveltejs/adapter-netlify';

export default {
	kit: {
		adapter: adapter({
			edge: false
			split:false
		})
	}
};
```
>[!note] svelte.config.js


- Include `netlify.toml` in the root of the folder.
```toml
[build]
	command = "npm run build"
	publish = "build"
```

git remote add origin git@github.com:TheShonuff/bfwellness.git
git push -u origin main

[[Working With Databases]]
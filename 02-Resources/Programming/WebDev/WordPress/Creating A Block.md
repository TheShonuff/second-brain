---
id: Creating A Block
aliases:
  - Wordpress create blocks
  - Creating A Block
tags:
  - wordpress
Created: 2024-01-14 14:12
title: Creating A Block
---
# Creating A Block
- Custom blocks are registered as plugins.
- The `create-block` generates a project with PHP, JavaScript, and CSS
- [WordPress create-block Tutorial](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/)
You can use the `create-block` to scaffold a block anywhere and use [[Local Enviroment|wp-env]] from inside the generated plugin folder.

Another option is to navigate to the `plugins/` and run the npm script
```sh
npx @wordpress/create-block@latest <project-name>
```
>[!note] <project-name> will define the internal block name

>[!tip] not providing a slug or project name will put the script into interactive mode. You'll be prompted for each input.

This will require a compile and build step
- `npm run start` for testing
- `npm run build` for production 

### Additional Information
[Registering a Block](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-registration/) 
[Edit and Save](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-edit-save/) - These functions provide the interface for how a block is going to be rendered, how it will operate and be manipulated, and how it will be saved.






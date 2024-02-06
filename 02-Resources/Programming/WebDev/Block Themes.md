---
title: Block Themes
Created: 2023-12-31 13:45
tags:
  - webdev
  - wordpress
aliases:
---
# Block Themes
- [[Theme Structure]]
	- [[functions.php]]
- [[Main Stylesheet]]

>[!warning] Avoid using closing `?>` tags at the end of files

## Including Assests
- [Assests Documentation](https://developer.wordpress.org/themes/core-concepts/including-assets/)
- Many block themes do not need to load any assets.
	- They can all be handled through the *global settings and styles*
- Before including assests use the utility functions for getting URLS and directorys paths.
	- `get_stylesheet_uri()` - Returns the active theme's `style.css` file url
	- `get_theme_file_uri( $file )` - Returns the active theme's URL
	- `get_parent_theme_file_uri( $file )` - Returns the parent theme;s URL
	- Directory Paths
		- `get_theme_file_path( $file )` 
		- `get_parent_theme_file_path( $file )`

## Global Settings and Styles
- [Global Setting Documentation](https://developer.wordpress.org/themes/global-settings-and-styles/)
- The `theme.json` is a standard file that WordPress looks for in your theme.
- The `theme.json` is a configuration file for how to style specific elements and blocks.

```json
{
	"$schema": "https://schemas.wp.org/trunk/theme.json",
	"version": 2,
	"settings": {},
	"styles": {},
	"customTemplates": {},
	"templateParts": {},
	"patterns": []
}
```
- `$schema` - Used to define the supported JSON schema
- `version` - The schema version
- `settings` - used to define your block controls and color paletters, font sizes
- `styles` - used to apply colors, font sizes, custom css
- `customTemplates` - Metadata for custome tempaltes defined in `/templates`
- `templateParts` - Metadata for template parts defined in `/parts`
- `patterns` - An array of pattern slugs to be registed from **pattern directory**



---
tags:
  - neovim
---
# NeoVim Themeing

## using Tokoynight with Transparent mode
```lua
{  
"folke/tokyonight.nvim",  
	opts = {  
		transparent = true,  
		styles = {  
		sidebars = "transparent",  
		floats = "transparent",  
		},  
	},  
}
```
>[!note] Make TokyoNight Transparent

>[!tip] Notify needds a background color. defaults to #000000

.config/nvim/lua/plugins/notify
```lua
require("notify").setup({
	background_colour = "#000000"
})
```

- Problem now is that there's a black background to the code completetions
- hrsh7th/nvim-cmp handles popup
	- specifically documentation window
```lua
vim.api.nvim_set_hl(0, "MyPemnu", {bg ="Black", fg = "White"})

window = {
	completion = cmp.config.window.bordered({
		border ="double",
		winhighlight = "Normal:Pmenu,FloatBorder:Pmenu,CursorLine:PmenuSel,Search:None"
	}),
}
```

          documentation = cmp.config.window.bordered({
            winhighlight = "Normal:Normal,FloatBorder:BorderBG,CursorLine:PmenuSel,Search:None",
          }),

Noice Pluging LSP > Progress
[nvim camp code](https://github.com/hrsh7th/nvim-cmp/blob/main/lua/cmp/config/window.lua)
[sample config](https://github.com/hrsh7th/nvim-cmp/issues/748)
[nvim discourse](https://neovim.discourse.group/t/how-to-configure-floating-window-colors-highlighting-in-0-8/3193)
[Reddit Post with Lsp_progress Transparency issue](https://www.reddit.com/r/neovim/comments/108w8wy/help_figuring_out_a_highlight_groups/)

```lua
vim.api.nvim_set_hl(0, “FloatBorder”, {bg=“#3B4252”, fg=“#5E81AC”})
```
`NoiceLspProgressTitle`
`NoiceLspProgressClient`
`NoiceFormatProgressTodo`

## Create Theme autocmd
- event is `ColorScheme`
- Check current auto event :au "event"
 
Check highlight groups using ":"":highlight"
Check
hl_pmenu (pop up menu)

### Don't Forget to 
- [ ] Disable noice / notify background color set it to $00000jk

## Highlight groups
- to search highlight groups `<leader>sH`

>[!note] All groups and edits can be configured at the source

Add italics for `@markup` treesitter for markdown in the TokyoNight Theme `line 253`
- `/local/share/nvim/lazy/tokyonight.nvim/lua/tokyonight` edit `theme.lua`
- 
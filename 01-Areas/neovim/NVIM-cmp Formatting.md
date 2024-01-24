---
tags:
  - neovim
---

---
Created: [[03-25-2023]]
tags: 
---
# NVIM-cmp Formatting
### Icons
```Lua
local vscode_symbols = {
	Text = "  ",
	Method = "  ",
	Function = "  ",
	Constructor = "  ",
	Field = "  ",
	Variable = "  ",
	Class = "  ",
	Interface = "  ",
	Module = "  ",
	Property = "  ",
	Unit = "  ",
	Value = "  ",
	Enum = "  ",
	Keyword = "  ",
	Snippet = "  ",
	Color = "  ",
	File = "  ",
	Reference = "  ",
	Folder = "  ",
	EnumMember = "  ",
	Constant = "  ",
	Struct = "  ",
	Event = "  ",
	Operator = "  ",
	TypeParameter = "  ",
}

```

scissor
&#9984
```LUA
formatting = {
		--appearance of popup window and completions --
		--	fields = { "kind", "abbr" },
		format = function(entry, vim_item)
			vim_item.kind = string.format("%s %s", vscode_symbols[vim_item.kind], vim_item.kind)
			--changed source_mapping to vscode_symbols
			--vim_item.menu = vscode_symbols[entry.source.name]
			vim_item.menu = ({
				buffer = "[Buffer]",
				nvim_lsp = "[LSP]",
				luasnip = "[LuaSnip]",
				nvim_lua = "[api]",
				cmp_tabnine = "[tabNine]",
			})[entry.source.name]
			if entry.source.name == "cmp_tabnine" then
				local detail = (entry.completion_item.data or {}).detail
				vim_item.kind = ""
				if detail and detail:find(".*%%.*") then
					vim_item.kind = vim_item.kind .. "" .. detail
				end
				if (entry.completion_item.data or {}).multiline then
					vim_item.kind = vim_item.kind .. " " .. "[ML]"
				end
			end
			local maxwidth = 80
			vim_item.abbr = string.sub(vim_item.abbr, 1, maxwidth)
			return vim_item
		end,
	},

	sources = {
		-- order ranks priority
		{ name = "nvim_lua" },
		{ name = "luansip" },
		{ name = "nvim_lsp", keyword_length = 4 },
		{ name = "cmp_tabnine" },
		{ name = "buffer", keyword_length = 5 },
	},
})

```




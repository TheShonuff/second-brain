---
tags:
  - neovim
---
# AutoCmd
- Nevim provides the following `autocm` functions
	- `nvim_create_augroup` - Greate or get an augroup
	- `nvim_create_autocmd` - Create an autocmd
	- `nvim_del_augroup_by_name` Delete augroup by name
	- `nvim_del_augroup_by_id` - Delete an augroup by id
	- `nvim_del_autocmd` - Delete an autocmd by id
	- `nvim_do_autocmd` - Do one autocmd
	- `nvim_get_autocmds` - Get autocmds that match the requirements


## Creating  Augroup
```Lua
nvim_create_augroup({name}, {*opts})
```
### Parameters
- **Name** *String*: The name of the group
- **Opts** *Dictionary Parametes*

### Example
```lua
local highlight_group = vim.api.nvim_create_augroup("YankHighlight", { clear = true })
vim.api.nvim_create_autocmd("TextYankPost", {
  callback = function()
    vim.highlight.on_yank()
  end,
  group = highlight_group,
  pattern = "*",
})

```
>[!note] Yank Highlight

## Creating AutoCmd
Creates an autocmmand event handler, defined by **callback** or **command**
```lua
nvim_create_autocmd({event}, {*opts*})
```
- **Event** *(string|array)* Event(s) that will trigger the handler (**callback** or **command**)
- **Opts** *Dictionary*
	- **Group** *(string|integer)*: optional: autocommand group name or id to mathc against
	- **Pattern** *(string|array)*: optional: pattern(s) to match literally
	- **Buffer** *(integer)*: optional: buffer number for buffer-local autocommands
	- **Desc** *(String)*: optional: descripition (for documentation and troubleshooting)
	- **Callback** *(Function|string)*: optional: lua function called when event is triggered.
		- id (number) autocommand id
		- event (string) name of the trigger event
		- group: (number|nil) autommand group id
		- match: (string) expanded value of `<amatch>`
		- buf: (number) expanded value of `<abuf>`
		- file: (string) expanded value of `<afile>`
		- data: (any) arbitrary data passed from `nvim_exec_autocmds`

>[!tip] For a full list of compatiable events `:help events`

### Example
```lua
vim.api.nvim_create_autocmd("BufReadPre", {
  pattern = "*",
  callback = function()
    vim.api.nvim_create_autocmd("FileType", {
      pattern = "<buffer>",
      once = true,
      callback = function()
        vim.cmd(
          [[if &ft !~# 'commit\|rebase' && line("'\"") > 1 && line("'\"") <= line("$") | exe 'normal! g`"' | endif]]
        )
      end,
    })
  end,
})

```
>[!note] Goto last location when opening buffer

Check events with :au "event"
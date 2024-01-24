---
creation date: 2022-11-22 02:05
aliases: []
tags: investigate
---

# Lua Language Server
LSP sumneko_lua INFO TOO large file: lua-language-server/log/large-file-library/large-file.lua skipped. The currently set size limit is: 500kb, and the file size is 2300kb.

more thatn 100000 files have been scanned... the current scanned directory is /home/shonuff/documents/ Please confirm if the configuration is correct. 

This would explain why the slow load time when opening lua files. Why is it doing this? Can I prevent the scanning when working in nvim??

Lua NVIM LSP seems to work correctly when a .luarc.json is located in the root of any project directory.

### Further reading 

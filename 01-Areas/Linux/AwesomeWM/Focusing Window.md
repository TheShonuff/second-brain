---
tags:
  - awesomewm
---

# Focusing Window

- **Clients** are windows
Some code that could work.
```lua
-- Grab focus on first client on screen
function grab_focus()
    local all_clients = client.get()
    for i, c in pairs(all_clients) do
        if c:isvisible() and c.class ~= "Conky" then
            client.focus = c
        end
    end
end
```


```lua
-- Bind all key numbers to tags.
...
if tags[screen][i] then
    awful.tag.viewonly(tags[screen][i])
    grab_focus()
end
```
[Source](https://superuser.com/questions/445371/focus-on-application-when-changing-workspaces-in-awesome-wm)

[Auto focus](https://www.reddit.com/r/awesomewm/comments/cj8cnv/requireawfulautofocus_doesnt_seem_to_work_how_can/?utm_source=share&utm_medium=ios_app&utm_name=ioscss&utm_content=2&utm_term=1)

[how to autofocus Reddit](https://www.reddit.com/r/awesomewm/comments/12erh9h/how_to_autofocus/?utm_source=share&utm_medium=ios_app&utm_name=ioscss&utm_content=2&utm_term=1)


[config resource](https://config.phundrak.com/Deprecated/awesome.html)

The **awful.client.focus.history.add** might contain a solution
The global key bind **Mod**+*tab* might have another key to the solution
```lua
awful.key({ modkey, }, "Tab", function () 
	awful.client.focus.history.previous() 
		if client.focus then client.focus:raise() 
		end 
	end, 
	{description = "go back", group = "client"}),
```

Left & Right nav backup
```lua
awful.key({ modkey, }, "Left", awful.tag.viewprev, {description = "view previous", group = "tag"}), 

awful.key({ modkey, }, "Right", awful.tag.viewnext, {description = "view next", group = "tag"}),
```


## Solution
```lua
awful.key({ modkey }, "Left", function(c)
	awful.tag.viewidx(-1)
	local master = awful.client.getmaster()
	awful.client.focus.byidx(1, master)
	end, 
	{ description = "Desktop Previous", group = "tag" }),
	
awful.key({ modkey }, "Right", function(c)
	awful.tag.viewidx(1)
	local master = awful.client.getmaster()
	awful.client.focus.byidx(1, master)
	end, 
	{ description = "Desktop Next", group = "tag" }),

```
>[!note] Will focus a client when the desktop (tag) is changed. It **will not** remeber what the client was that was last highlight


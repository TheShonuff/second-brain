---
tags:
  - awesomewm
  - linux
---
# AwesomeWM
[[AwesomeWM Freezing Issue]]
[Arch AwesomeWM](https://wiki.archlinux.org/title/awesome)
- AutoStart Plugins
	- Compositor = **picom**
	- wallpaper = **nitrogen**
[[Dracula Color Theme]]
[[Tokyo Night Strom Color Scheme]]
Crashing
[no arb](https://awesomewm.org/apidoc/documentation/09-options.md.html#modelines)

[[AwesomeWM notifications]]

[Awesome Widget](https://github.com/streetturtle/awesome-wm-widgets/tree/master)
- Issue with volume widget.
	- Wants to use pulse audio
	- Currently using pipewire-pulse

## Helpful keybinds
- **Super** *s* - shows current keybindings

## Modular Config
- rc.lua
	- main
		- *error-handling.lua*
		- *layouts.lua*
		- *menu.lua*
		- *rules.lua*
		- *signals.lua*
		- *tags.lua*
		- *user-variables.lua*
	- deco
		- *statusbar.lua*
		- *taglist.lua*
		- *tasklist.lua*
		- *titlebar.lua*
		- wallpaper.lua
	- binding
		- *bindtotags.lua
		- *clientbuttons.lua*
		- *clientkeys.lua*
		- *globalbuttons.lua*
		- *globalkeys.lua*
			- Configures popup help, browsing, standard programs, layout manipulation

Monitor config 
DP-1  connected 3840x2160+0 (normal left inverted right x axis y axis) 697 x 392mm
DP-2 connected 1200X1920 left (normal left inverted right x axis y axis) 518mm x 324mm

[Glib Date Time Format](https://docs.gtk.org/glib/method.DateTime.format.html)
[Helpful layout information](https://awesomewm.org/doc/api/documentation/03-declarative-layout.md.html)
[[LightDM]]
[[Focusing Window]]
[Pango Markup Cheat Sheet](http://irtfweb.ifa.hawaii.edu/SoftwareDocs/gtk20/pango/pangomarkupformat.html)

ToDo's
- [x] Display different wall paper for each screen
- [x] Format help menu
- [ ] Get File Menu for app
- [x] LightDM Login Screen Monitor orientation
- [x] Install Ranger
- [x] Focus next window if one closes on current screen
- [x] auto focus when tag changed - rule?
- [x] Close window shortcut . Currently mod shift c ? Note: function in client keys
- [ ] Setup Tags on "Notes" Monitor
	- [ ] Notes
	- [ ] Mangament
	- [ ] Documentation
- [ ] Setup Tags on "Primary"



---
id: Display Manager
aliases:
  - Display Manager
tags:
  - linux
---

# Display Manager

A display manager, or login manager, is typically a graphical user interface that is displayed at the end of the boot process in place of the default shell.

There are various types of Display Managers just like there are various types of [[1706044697-window-managers|window managers]] and [[1706044718-dekstop-environments|dekstop environments]]

## List of Display Managers I have used

- greetd (active)
- SDDM
- [[LightDM]]

# Trouble Shooting

Check if wayland is active

```Sh
echo $XDG_SESSION_TYPE
```

```sh
echo $DESKTOP_SESSION
```

Check enviroment variables

```sh
env | grep -i wayland
```

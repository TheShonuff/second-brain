---
title: WirePlumber
Created: 2023-09-27 19:37
tags:
  - linux
aliases:
---

---
# WirePlumber
- Session and policy manager for [[PipeWire]]. 
- [Arch Wiki](https://wiki.archlinux.org/title/WirePlumber)

## Configuration
- `~/.config/wireplumber`
- `wireplumber.comf` the default configuration. includes functionality of all the other configurations within one process
- `main.conf` Loads the modules and components necessary for WirePlumber core.
- `blutetooth.conf` handles bluetooth connectivity.
- `policy.conf` how wireplumber makes decisions about moving and making changes to nodes.

- It's recommended to add a lua script to the relevant `lua.d` folder.

## Obtaining Interface names 
- `wpctl status`
- `wpctl inspect <number>`

## Commands
`set-default` will set the default sink

## Show Volume
`wpctl get-volume @DEFAULT_AUDIO_SINK@`
---
tags:
  - linux
  - hypr
aliases:
  - hyprland
---

# HyprLand

Enable GreetD
`systemctl enable greetd.service -f`

## Monitors 
[Monitor Configuring](https://wiki.hyprland.org/Configuring/Monitors/)
list monitors with `hyprctl monitors

## Workspaces
Relative workspaces

Date Formatting
[Stream Formatting](https://howardhinnant.github.io/date/date.html#to_stream_formatting)


Restart Waybar
`killall -SIGUSR2 waybar`

Screenshots
`hyprshot -m region`

## Sound Not Working
`alsamixer` command to check sound outputs
removed wireplumber for pipewire-media-session
`alsactl init`

stored in `/usr/share/alsa/init/directory` top level configuration is `00main`

`aplay --list-devices --list-pcms`

`lsmod | grep snd_hda_intel`

[Alsa Arch wiki](https://wiki.archlinux.org/title/Advanced_Linux_Sound_Architecture#Tips_and_tricks)


working with 
Profile -> Pro Audio
Built-in Audio -> Analog Stereo Output

HDA-Intel "RealTek ALC892" Motherboard Card
HDA-Intel Nvidia GPU 84 HDMI/DP
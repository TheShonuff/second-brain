---
tags:
  - linux
---


# Fixing DPI
- Added to `/etc/sddm.conf`
```shell
[X11] ServerArguments=-nolisten tcp -dpi 96
```

- Added dropin file `/etc/sddm.conf.d/hidpi.conf`
```shell

```

[ArchWiki](https://wiki.archlinux.org/title/Xorg#Display_size_and_DPI)

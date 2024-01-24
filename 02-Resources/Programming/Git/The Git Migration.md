---
tags:
  - git
---

---
Created: [[05-30-2023]]
tags: 
---
# The Git Migration
- Update your system and merge the pacman pacnew `/etc/pacman.conf.pacnew` 
```shell
pacman -Syu "pacman>=6.0.2-7"
```


Check difference
```shell
diff /etc/pacman.conf.pacnew /etc/pacman.conf
```

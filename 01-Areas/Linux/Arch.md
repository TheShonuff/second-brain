---
title: Arch Linux
tags:
  - linux
  - arch
"type:": moc
---
# Arch
- pacman is the **package manager**
	- combines a simple binary package with an easy-to-use build system
- Install a specific package `pacman -S "package_name1" "package_name2" `
- Remove a package `pacman -R "package_name"`
- Upgrade package `pacman -Syu`
- Upgrade packages and recreate database `pacman -Syyu`


## Firewall
>[!note] You'll need to start and stop the firewall to do any testing with **VITE** or any services that require access *localhost*

```shell
systemctl start firewalld
systemctl stop firewalld
systemctl status firewalld
firewall-cmd --state
```

## File Explorers
- [[Ranger Shortcuts]]
- [[Yazi]]
## Enabling Greeters
```shell
systemctl enable greetd.service -f
systemctl enable lightdm.service -f
systemctl enable gdm.service -f
```

- greetd configuration `etc/greetd`
## Aur
- Arch User Repository
- Compile and build packages with <code>makepkg</code>
>[!tip] It's good practice to always inspect packages

- A helper called [yay](https://github.com/Jguer/yay) exists to make installing packages easier

| Command                            | Description                                                                                      |
| ---------------------------------- | ------------------------------------------------------------------------------------------------ |
| <code>yay</code>                   | Alias to <code>yay -Syu</code>                                                                   |
| <code>yay "search" </code>         | Present package-installation selection menu                                                      |
| <code>yay -Bi "dir"</code>         | Install dependencies and build a local PKBUILD                                                   |
| <code>yay -G "AUR Package"</code>  | Download PKBUILD FROM ABS or AUR                                                                 |
| <code>yay -Gp "AUR Package"</code> | Print stdout PKBUILD from ABS or AUR                                                             |
| <code>yay -Ps</code>               | Print system statistics                                                                          |
| <code> yay -Syu -devel</code>      | Perfrom system upgrade, but also check for development package updates                           |
| <code>yay -Syu --timeupdate</code> | Perform system upgrade and use PKBUILD modification time(not version number) to determine update |
| yay -Ss <"package name">           | Lists packages and will include an "Installed" item next to it if installed                      |
### Without Helper
```bash
git clone <package_url>
cd <package_name>
makepkg -si
```

[[Linux Fonts]]

### Taking a screenshot
```shell
scrot -s

hyprshot -m region
```
>[!note] Starts a selection screenshot and save to ~/

## Use NVIM In Sudo
```Shell
sudo -E -s nvim <file-name>
```

## Pacman Backup
[Documentation](https://wiki.archlinux.org/title/pacman/Tips_and_tricks)
```sh
tar -cjr pacman_database.tar.bz2 /var/lib/pacman/local
```

```sh
tar -cjf pacman_database.tar.bz2
```
>[!note] move the tarball in the `/` directory and execute the command



[[Fixing DPI]]

[wiki](https://wiki.archlinux.org/title/NVIDIA)
[Endeavour Guide](https://discovery.endeavouros.com/nvidia/new-nvidia-driver-installer-nvidia-inst/2022/03/)

[[Display Manager]]

[[Rofi]]

## Audio
[[PipeWire]]
```shell
alsactl init
```

## Fonts
- list all fonts `fc-list`


## Zsh Modifications
### Zoxide
- [Github](https://github.com/ajeetdsouza/zoxide)
### FZF
- Use `ctrl-t` in terminal to find

[[The Git Migration]]
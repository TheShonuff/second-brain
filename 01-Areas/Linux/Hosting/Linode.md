---
tags:
  - linode
  - linux
---
# Linode

## Getting Started
- [Official Guide](https://www.linode.com/docs/products/platform/get-started/)
- [Creating a Compute Instance Doc](https://www.linode.com/docs/products/platform/get-started/)
	- [Chossing a linux distribution](https://www.linode.com/docs/products/compute/compute-instances/guides/distributions/)
	- [Generating SSH Keys](https://www.linode.com/docs/guides/use-public-key-authentication-with-ssh/)
- [Installing LAMP](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-22-04)
- [Installing and configure WordPress](https://www.linode.com/docs/guides/how-to-install-wordpress-ubuntu-22-04/)
	- [Word Press Best Practices](https://www.linode.com/docs/guides/configuring-wordpress/)

**Domain Name Servers**
ns1.linode.com
..
ns5.linode.com

---


[SSh Config](https://linuxhandbook.com/enable-ssh-ubuntu/)
<code>/etc/ssh/sshd_config</code>
1. create .ssh folder in home
2. create *authorized_keys* file
3. chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys
4. sudo systemctl restart sshd

### Add Sudo user
```Shell
sudo adduser <username>
sudo usermod -aG sudo <username>
```

## Install ZSH
```sh
sudo apt install zsh -y
```

#### Display Shells
```Shell
cat /etc/shells
```
#### change shell
```sh
sudo chsh -s /bin/zsh
```

##### Required Plugins 
```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
git clone https://github.com/zsh-users/zsh-autosuggestions

# source in ZSH

```
### fzf
```
sudo apt install fzf
```

### RipGrep
```
sudo apt-get install ripgrep
```
### Copy Enviroment
```shell
ech ".dotfiles" >> .gitignore
git clone --bare https://github.com/TheShonuff/.config.git $HOME/.dotfiles
config checkout -f
config submodule update --init
config config --local status.showUntrackedFiles no
```

## FNM (Node)
[FNM Github](https://github.com/Schniz/fnm)
```sh
curl -fsSL https://fnm.vercel.app/install | bash
```


### NPM
[[Node]]
[[NPM Currently Installed Packages]]
```

### Installing NVIM
```Shell
sudo add-apt-repository ppa:neovim-ppa/stable
sudo apt-get update
sudo apt-get install neovim
```
>[!Note] [Documentation](https://github.com/neovim/neovim/wiki/Installing-Neovim)


For chezmoi [Installing Go](https://www.digitalocean.com/community/tutorials/how-to-install-go-on-ubuntu-20-04)
```Shell
curl -OL https://golang.org/dl/go1.20.3.linux-amd64.tar.gz
sudo tar -C /usr/local -xvf go1.20.3.linux-amd64.tar.gz
```

## hook up github
[Linode Github Documentation](https://www.linode.com/docs/guides/a-beginners-guide-to-github/)
# Wordpress notes
- To setup the theme directory as a git repo you'll need to change the permissions of the working folder.
```Shell
sudo chown -R username.group path/to/file_or_dir
```

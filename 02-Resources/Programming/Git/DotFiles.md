---
tags:
  - git
---

## Non-bare
Has a *.git* folder, which is the backbone of the repository where all the important files for tracking the changes in the folder are stored. 
## bare
Same as a default, but no commits can be made in a bare repository. The changes made in projects cannot be tracked by a bare repository as it doesn't have a working tree. It's a *.git* folder with a specific folder wher all the project files reside.
### Reference Links
[Atlassian](https://www.atlassian.com/git/tutorials/dotfiles)
[Ackama says](https://www.ackama.com/what-we-think/the-best-way-to-store-your-dotfiles-a-bare-git-repository-explained/)
[Storing Dotfiles in a Git Repository](https://www.ackama.com/what-we-think/the-best-way-to-store-your-dotfiles-a-bare-git-repository-explained/)

----
```sh
git init --bare $HOME/.dotfiles
```
This creates a **bare** git repository at *~/.dotfiles*. Next an alias will need to be setup to interact with the directory. In *.zshrc*
```sh
# DotFiles
alias config="git --git-dir=$HOME/.dotfiles --work-tree=$HOME"
```
The *--work-tree=$HOME* option sets the directory that the repo tracks to your home directory. There are a bunch of files in the home directory that should not be in the repo. We can configure the repo to not show untracked files by default.
```sh
config config --local status.showUntrackedFiles no
```
In order to **track files** we need to add. From any directory on the disk you can run something similiar
```sh
config add ~/.bashrc
config commit -m "added bash file"
```

# Script to install on new system
*need to update with personal github settings* #script
```sh
#!/usr/bin/env bashgit clone --bare git@github.com:mrjones2014/dotfiles.git $HOME/.dotfiles# define config alias locally since the dotfiles  
# aren't installed on the system yet  
function config {  
   git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME $@  
}# create a directory to backup existing dotfiles to  
mkdir -p .dotfiles-backup  
config checkout  
if [ $? = 0 ]; then  
  echo "Checked out dotfiles from https://github.com/TheShonuff/config.git";  
  else  
    echo "Moving existing dotfiles to ~/.dotfiles-backup";  
    config checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | xargs -I{} mv {} .dotfiles-backup/{}  
fi# checkout dotfiles from repo  
config checkout  
config config status.showUntrackedFiles no
```
**Before installation** *make sure the alias is set in the .zsh* on the new computer.
```sh
alias config="git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME"

```
Now simply run the following command.
```sh
curl https://raw.githubusercontent.com/mrjones2014/dotfiles/master/scripts/config-init | bash
```
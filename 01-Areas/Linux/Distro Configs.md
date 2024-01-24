---
tags:
  - linux
---
# Distro Configs
[[NVIM Update]]


```start-multi-column
ID: ID_2rfn
Number of Columns: 2
Largest Column: standard
```

```start-multi-column
ID: ID_2rfn
Number of Columns: 2
Largest Column: standard
```

[[System Backup]]
### Distro Configs
- [[Linode]]
- [[AwesomeWM]]
- [[Arch]]

## XDG Journey
<code>.zshenv</code> holds the key
```Shell
export XDG_CACHE_HOME="$HOME/.cache" export XDG_CONFIG_HOME="$HOME/.config" export XDG_DATA_HOME="$HOME/.local/share"
```
relevant [reddit post](https://www.reddit.com/r/zsh/comments/wycqlq/move_config_files_away_from_home/)

Fnm config change

eval "$(fnm env --use-on-cd  --verison-file-strategy=recursi)"
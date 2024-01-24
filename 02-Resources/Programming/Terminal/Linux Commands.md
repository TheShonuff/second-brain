---
tags:
  - terminal
---
# Linux Commands
## Zip
```sh
zip -r -q <fileName> <FolderToBeZipped>
```

## Kitty SSH

```bash
kitty +kitten ssh -l vagrant <ip-address>
```

## FZF
*alt* **c** - will change directory (cd) into a directory
*ctrl* **r** - interactive finder
### Auto-Completion
```Shell
$ cat ** <TabKey>
$ export ** <TabeKey>
```
> [!note] When tab is pressed it will activate fuzzy finder

## Editing fiiles

sudo -E -s

## Managing Disks
- use <code>df</code> to locate disks.
	- <code>lsblk</code> offers a different view of disks and partitions
- Then unmount the disk to interact with it.

```bash
df -hT
sudo umount /dev/sdc1
sudo mkfs.vfat /dev/sdc1

```
>[!note] Steps to format disk

```bash
sudo fsck /dev/sdc1
```
>[!note] To confim disk was formatted


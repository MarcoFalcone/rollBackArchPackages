# rollBackArchPackages
roll back to previous version of packages in case of a feature break after update.
We are going to do this by changing the date of the arch archive the our system is using and do a system update(downgrade).

### create a back up file of mirror list
$ sudo cp /etc/pacman.d/mirrorlist{,.bak}

### open the mirror list file
$ sudo vim /etc/pacman.d/mirrorlist

### change the content with the following
### Arch Linux repository mirrorlist
### Created to downgrade to "date"
Server=https://archive.archlinux.org/repos/YYYY/MM/DD/$repo/os/$arch

### update system(downgrade)
$ sudo pacman -Syyuu

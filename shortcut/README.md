## Add Shortcut in Linux

This tutorial enables creation of a shortcut for **Cemu Emulator**.

It assumes you have either cloned the repository or downloaded and extracted [the zip file](https://github.com/leomaurodesenv/cemu-linux/archive/master.zip).

Files in this repository:
- `cemu.ico`: cemu icon.
- `cemu.png`: cemu icon.
- `cemu.desktop`: cemu shortcut.
- `wine-emulator`: new command line.

### Create a Command

```shell
#- open this folder
$ cd [..]/cemu-linux/shortcut

#- create a new command 'wine-emulator'
#  enable cemu performance by a one command line
$ sudo cp wine-emulator /usr/bin/
$ sudo chmod +x /usr/bin/wine-emulator
```

### Create the Shortcut

```shell
#- change the main directory
#  change the username in: /home/username/[..]
#  replace with the user name of your computer
$ gedit cemu.desktop

#- create icon image folder
$ sudo mkdir /snap/icon
#- copy the icons
$ sudo cp cemu.ico /snap/icon
$ sudo cp cemu.png /snap/icon

#- copy desktop
#  note: /usr/share/applications is the applications
#  folder for Ubuntu SO, for other Linux the path may change
$ sudo cp cemu.desktop /usr/share/applications
```

Search for: Cemu Emulator (in your Applications).
Enjoy!

---

## Also see ~

- Created by Leonardo Mauro (leo.mauro.desenv@gmail.com)
- GitHub: [cemu-linux](https://github.com/leomaurodesenv/cemu-linux)

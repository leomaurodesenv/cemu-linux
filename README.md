# Cemu in Linux

Steps to using Cemu with Wine works for any game!   
   
Important links:
- [Cemu](http://cemu.info/#download): Wii U emulator.
- [Cemu Graphic Packs](https://github.com/slashiee/cemu_graphic_packs/releases): graphic packs that improve games graphics.
   
**Features**:
- `/shortcut/`: steps to create a shortcut for Cemu in Linux.
- `README.md`: steps to install Cemu, wine, drivers and some features.
   
---
## Summary

- [Wine](#wine)
    - Installing
    - Settings
        - Configuration
        - More features
- [Drivers](#drivers)
    - AMD or Intel Graphics
    - Nvidia
- [Cemu](#cemu)
    - Installing
    - Graphic Packs
    - Performace
- [Additions](#additions)
    - Joystick
    - Play!
- [Cemu Bonus](#cemu-bonus)
    - Add Cemu shortcut
    - How to download updates and DLC
    - Improvement for Cemu
   
---
## Wine

### Installing

```shell
#- add apt key
$ wget -nc https://dl.winehq.org/wine-builds/winehq.key && sudo apt-key add winehq.key && sudo apt update

#- add wine official repository
$ sudo apt-add-repository https://dl.winehq.org/wine-builds/ubuntu/
$ sudo apt-get update

#- install
$ sudo apt-get install --install-recommends winehq-stable

#- check version
$ wine --version
```

### Settings  

Open the settings:
```shell
#- open wine settings
$ winecfg

#- Application
# Select: Windows version: Windows 10
# Select: Apply and OK
```

Installing more features:
```shell
#- winetricks
$ sudo apt install winetricks

#- installing Microsoft Visual C++ 2015 or 2017 (choose only one)
$ bash winetricks vcrun2015
$ bash winetricks vcrun2017 # (recommended)
```

---
## Drivers

AMD or Intel Graphics Technology:
```shell
$ sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
$ sudo apt update && sudo apt dist-upgrade
$ sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```

Nvidia:
```shell
$ sudo add-apt-repository ppa:graphics-drivers/ppa
$ sudo apt update && sudo apt install nvidia-driver-396
```

---
## Cemu

### Installing

```shell
#- open official link to down the last release
$ xdg-open http://cemu.info/#download

#- unzip the cemu
$ mkdir ~/cemu
$ unzip cemu_x.xx.x.zip -d ~/cemu
$ mv ~/cemu/cemu_x.xx.x/* ~/cemu/ # reorder files
$ rm ~/cemu/cemu_x.xx.x # remove blank folder

#- open cemu folder
$ cd ~/cemu
```

### Graphic Packs 

```shell
#- open official link to download the last release
$ xdg-open https://github.com/slashiee/cemu_graphic_packs/releases

#- Download graphic packs
# Extract files to: ~/cemu/graphicPacks/
$ unzip graphicPacksxxx.zip -d ~/cemu/graphicPacks/
```

### Performace

```shell
#- execute cemu
$ vblank_mode=0 mesa_glthread=true R600_DEBUG=nohyperz wine ~/cemu/Cemu.exe

#- Configuration by the menu
# Select: Options > GPU buffer cache accuracy > Low (fast)
# Select: CPU > Mode > Single-core recompiler (fast)
```

---
## Additions

### Joystick

```shell
#- installations
$ sudo apt-get install joystick
$ sudo apt-get install jstest-gtk

#- calibrate your joystick
$ jstest-gtk
```

### Play!

```shell
#- open cemu
$ cd ~/cemu

#- run
$ vblank_mode=0 mesa_glthread=true R600_DEBUG=nohyperz wine Cemu.exe

#- add a game
# Select file: (Menu) File > Install Update/DLC
# Launch to game folder ~ directories starting with 0005000C and 0005000E
# Open the file: [..]/0005000xxxxxxxxx/meta/meta.xml
# Show up: Updated with success!

#- running a game
# Select file: (Menu) File > Load
# Launch to game folder ~ directories starting with 0005000C and 0005000E
# Open the file: 0005000xxxxxxxxx/code/*.rpx # each game have your filename.rpx
```

---
## Bonus

### Cemu Shortcut

See [/shortcut](/shortcut) to add a Cemu shortcut.   

### Cemu Improvements

If you looking for improvements, new joysticks and so on.   
Read about [Cemuhook](https://cemuhook.sshnuke.net/), some [projects](https://github.com/search?q=cemuhook&type=Repositories).   
   
---
### Also look ~

- [Contributors](CONTRIBUTORS.md)
- License: [MIT](LICENSE)
- Create by Leonardo Mauro (leo.mauro.desenv@gmail.com)
- GitHub: [leomaurodesenv](https://github.com/leomaurodesenv/)
- Site: [Portfolio](http://leonardomauro.com/portfolio/)

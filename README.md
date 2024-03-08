# mpd

Plymouth is an application that runs very early in the boot process (even before the root filesystem is mounted!) that provides a graphical boot animation while the boot process happens in the background.

This repo is intended for [Volumio music player](https://volumio.com/) MPD enhancements for armfh.

### Contents


| Folder           | Content                                              |
| ------------------ | ------------------------------------------------------ |
| /packages/static | Compiled and ready to use packages for Volumio3.     |
| /packages/debug  | The usual – extra debug packages for curious minds. |
| /sources         | Complete sources for this build.                     |

## Build notes

This is not a complete guide, only set of essential instructions for this build:

### Update your locale by appending exports:

**nano ~/.bashrc**

```
# Setting for the new UTF-8 terminal support in Volumio
export LC_CTYPE=en_US.UTF-8
export LC_ALL=en_US.UTF-8
```
```
source ~/.bashrc
```
### Update repos:

**sudo nano /etc/apt/sources.list**

```
deb-src http://raspbian.raspberrypi.org/raspbian/ buster main contrib non-free rpi
```

sudo apt update

### Install essential build packages:

sudo apt install build-essential fakeroot devscripts

### Install build required packages:

sudo apt install cmake 

### Install mpd dependencies:

sudo apt build-dep plymouth

### Run build:

debuild -b -uc -us

*or complete with sources*

debuild -uc -us

---

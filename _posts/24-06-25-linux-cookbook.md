---
title: Linux cookbook
date: 2024-05-23
categories: [Cookbook]
tags: [Linux, Parrot, Kali, cookbook]
---

## Linux directory structure

| path | meaning | intended for |
| ---- | ------- | ------------ |
| `/bin` | binaries | Executables and binary files |
| `/boot` | getting ready | Contains all the boot-related files e.g. conf, grub, etc. |
| `/dev` | devices | Dynamically created files representing devices as they are connected |
| `/etc` | configuration files | Host specific configuration files |
| `/home` | user filesystem | Contains user specific home catalogs |
| `/lib` | libraries | Functionalities shared between different applications |
| `/opt` | optional | Optional and third-party software |
| `/proc` | processes | Pseudo-files representing running processes |
| `/root` | | Home folder of the root superuser |
| `/sbin` | superuser binaries | Executables and binary files that requires root privileges |
| `/tmp` | temporary | Temporary filesystem, typically cleared on reboot |
| `/var` | variables | Contains things that are prone to change, such as websites, temporary files, databases |

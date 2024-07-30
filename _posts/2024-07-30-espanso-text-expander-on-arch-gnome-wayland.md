---
title: Running Espanso Text Expander on Arch Linux Wayland using Dvorak
layout: post
categories:
  - Arch
  - Linux
  - Automation
---

## Context

I wanted to use a text expander on my machine running Arch and Wayland with a keybard layout of Dvorak. Here are some notes for my future self and others trying to do the same to make it a smoother experience.

[![screenshot showing arch linux system details](/assets/2024/07/2024-07-30-fast-fetch-arch.png)](/assets/2024/07/2024-07-30-fast-fetch-arch.png)

I installed Espanso using `yay -S espanso`. Then followed the instructions at [https://espanso.org/docs/install/linux/#install-on-wayland](https://espanso.org/docs/install/linux/#install-on-wayland)
Don't forget to give Espanso required capabilities by running the setcap command on the install page.

Since I am running a Dvorak keyboarad layout, I had to add the following configuration to the end of my ~/.config/espanso/config/default.yml

```
keyboard_layout:
  rules:      "evdev"
  model:      "pc105"
  layout:     "us"
  variant:    "dvorak"
```

When I run the docs recommended command to determine my current settings I get a partially workin response:

```
$ setxkbmap -query
WARNING: Running setxkbmap against an Xwayland server
rules:      evdev
model:      pc105
layout:     us
```

After properly setting my keyboard layout in the default.yml config file, Espanso is working for me.
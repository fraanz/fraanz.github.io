# flyby
## Doc & tools to get a minimal, stable and simple environment on top of gentoo linux

The purpose of this repo is to be a reference for me (and other people I hope) in the configuration of an unix-like operating system from scratch. If you are new in the unix world, you may miss an overview of the components needed to get a fully working environment. Even if you are a more experienced user (not my case anyway), you may want a skeleton for a fast basic configuration of new systems. **Remember: the best configuration tool is the wiki.** So you can consider this like an attempt to build a my own operating system :P

Beware, these istruction are only to get the *my* small, cute, stable operating system. Obviously you should be free to skip whatever step you are not interested in. For any doubt, refer to the [gentoo wiki](https://wiki.gentoo.org/).

So, let's start with some notes...


### Boot
 * You may want to disable kernel messages during the boot process. To do so, add the 'quiet' parameter on kernel commandline. If you are using grub, you need to modify /etc/default/grub and add it on GRUB_CMDLINE_LINUX_DEFAULT. Remember to regenerate the bootloader configuration file when you are done! (grub-mkconfig -o /boot/grub/grub.cfg)
 * TODO: replace grub with lightweight alternative/disable openrc messages
 
### Display Manager
If you have to start X, you can rely on the dm for this task. Also, this way you will able to use preconfigured X sessions instead of having to write your own startup commands. Currently I'm using SLIM, seems lighter even than LightDM.

### Window Manager
After obtaining access to the X server, a wm is needed to manage multiple X clients (=windows); if you are an hardcore minimalist you can rather spawn a terminal emulator with a terminal multiplexer within. There are a lot of wm with different paradigms; I used for a long time the i3wm (tiling) but I plan to try dwm, the suckless.org window manager. Also, fvwm is an option to consider for non-tiling wm, since it has been here for over 25 years and it's still working!

### Application menu
With only a window manager you will not be able to do anything, except for those with an integrated menu. Thus an app menu is needed: you can try for example the [j4-dmenu-desktop]([https://github.com/enkore/j4-dmenu-desktop), which is based on dmenu (another suckless tool) and is able to parse .desktop files (they contain a description of gui applications). Remember to assign the menu command to a keybind, otherwise you will not be able to use it :P

### Status bar
Ya, you got a menu, you can open and manage multiple windows, but... something still missing? Yes, you can't have an overview of the system without having to open a terminal. To solve this issue, and if you have enough space on the screen, you can add to startup entries of your wm a desktop bar. Like everything in linux there are many alternatives for every software; i3 has its own i3bar, I also heard of i3blocks, polybar and my friend's (Allah ak)[vbar](https://github.com/vbextreme/vbar).


To be continued... you feel something is missing or wrong? Try to make a PR, I'll take a look.

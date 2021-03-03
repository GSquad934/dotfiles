# My LeftWM Configuration
![](https://hostr.co/file/QafECpyxH4e1/leftwm.png)

This repository hosts the configuration files for [LeftWM](https://leftwm.org/). The files here consist of a *config.toml* file that contains all the key bindings of the window manager. The rest is part of a custom theme. It features:

* Status bar with *Polybar* with a built-in system tray
* Script to autostart all the necessary programs such as the composer, etc...
* 9 workspaces
* Custom scripts ran by the status bar to display various information

# Dependencies
The following packages are necessary in order to run this build of DWM properly:

* ttf-jetbrains-mono
* ttf-joypixels
* libxft-bgra
* feh (recommended)
* dmenu (recommended)
* alacritty (the hard-coded terminal in the *config.toml* file)
* xlock (optional, only if you want a lock screen)

If you want a nice DMenu to be integrated, you can install [my custom build](https://github.com/GSquad934/dmenu). The default terminal emulator can be modified to any out there.

# Installation
For Arch based Linux distributions, LeftWM is available in the AUR. Use any AUR helper you want to install this window manager. Here is the necessary command if using *YAY*:

```
yay -S leftwm
```

For other methods of installation, please refer to the documentation on the [LeftWM Github page](https://github.com/leftwm/leftwm).

# Running LeftWM
If you don't use a login manager, you can start the graphical environment with the *startx* command (package "*xorg-xinit*" required) and a properly configured *.xinitrc* file. If you want some inspiration for your *.xinitrc*, you can check out [mine](https://github.com/GSquad934/dotfiles/blob/master/config/X11/xinitrc).

If you use a login manager (such as *lightdm*), LeftWM package installation should have already created a *.desktop* file necessary for the login manager. Otherwise, make sure to create a *leftwm.desktop* file in */usr/share/xsessions/*. The file should contain the following:

```
[Desktop Entry]
Encoding=UTF-8
Name=LeftWM
Comment=A window manager for the adventurer
Exec=leftwm
Type=Application
```

# Key Bindings
I configured the key bindings that I like. They are all configured in the *config.toml* file. Here is the full list and what they actually do:

* **MODKEY** has been configured to be the Super key (=Windows key)

| Key binding | Action |
| :--- | :--- |
| `MODKEY + RETURN` | Open terminal (alacritty is the hard-coded one but it can be modified) |
| `MODKEY + SHIFT + RETURN` | Open run launcher (dmenu is the run launcher but it can be modified) |
| `MODKEY + SHIFT + c` | Close window with focus |
| `MODKEY + SHIFT + r` | Soft reload LeftWM  |
| `MODKEY + SHIFT + q` | Quit LeftWM |
| `MODKEY + 1-9` | Switch focus to workspace (1 to 9) |
| `MODKEY + SHIFT + 1-9` | Send focused window to workspace (1 to 9) |
| `MODKEY + j` | Focus stack +1 (switches focus between windows in the stack) |
| `MODKEY + k` | Focus stack -1 (switches focus between windows in the stack) |
| `MODKEY + i` | Move focused window at the top of the stack (=master) |
| `MODKEY + SHIFT + j` | Rotate stack +1 (rotates the windows in the stack) |
| `MODKEY + SHIFT + k` | Rotate stack -1 (rotates the windows in the stack) |
| `MODKEY + h` | Decrease focused window width |
| `MODKEY + l` | Increase focused window width |
| `MODKEY + right` | Switch to the next workspace |
| `MODKEY + left` | Switch to the previous workspace |
| `MODKEY + l` | Increase focused window width |
| `MODKEY + Tab` | Cycle to the next layout |
| `MODKEY + SHIFT + Tab` | Cycle to the previous layout |
| `MODKEY + SHIFT + w` | Move to the last workspace |
| `MODKEY + w` | Swap tags |
| `MODKEY + ALT + l` | Lock the screen |

<u>**Note**</u>: the key bindings in this configuration are a bit limited because I actually use SXHKD to run all my applications. My configuration for *SXHKD* can be found in [my dotfiles](https://github.com/GSquad934/dotfiles/blob/master/config/sxhkd/sxhkdrc). My configuration file for *SXHKD* is totally based on my personal dotfiles, so you will need to modify either the key bindings of LeftWM or have a custom *sxhkdrc* ready.

# Status Bar
In the custom theme offered by this repository, [Polybar](https://github.com/polybar/polybar) has been configured to act as the status bar

![](https://hostr.co/file/zFlwYKUQmtMi/leftwm_bar.png)

* 📦 0 : indicates how many updates are available (script: *updates.sh*)
* 🖥️ 2%: indicates the CPU usage
* 🧠 35% : indicates the RAM usage
* ⬇  120B ⬆  60B : indicates the download/upload network traffic usage. It will automatically change B/KB/MB depending on the usage
* 💾 8.2G (38%) : indicates the disk space usage where "/" is mounted. Other disks can be added by modifying the script
* 🌡 25.2 : indicates the CPU temperatur
* 🔊 60% : indicates the volume level. The icon will change depending on the volume level
* 🕒 Wed, February 24 21:39 : indicates the current day, date and time in 24H format
* The system tray on the right will display whatever icon is required in the systray

While certain information are internal to *Polybar*, others actually require the usage of scripts. All scripts are part of the theme and can be found in the *themes/mytheme/scripts* folder.

# Wallpapers
*Feh* is used to setup the wallpaper. A default wallpaper (file: *background.jpg*) is supplied with this theme for LeftWM. However, it is possible to setup a custom wallpaper by either replacing the file *themes/mytheme/background.jpg* or by storing some custom wallpapers in a folder such as *$HOME/.local/share/wallpapers* and modify the command in the *themes/mytheme/up* file to be:

```
feh --bg-fill --no-fehbg --randomize "$HOME"/.local/share/wallpapers*
```

If you want a set of nice wallpapers, I have some stored in this [repository](https://github.com/GSquad934/wallpapers).

# Contact
You can always reach out to me:

* [Twitter](https://twitter.com/gaetanict)
* [Email](mailto:gaetan@ictpourtous.com)
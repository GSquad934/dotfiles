# Dotfiles

![](https://hostr.co/file/VvyK1CyZGELf/dotfiles-showcase.png)

This repository hosts all my public configuration files. They offer the following features:

* Modular configuration of $SHELL (BASH & ZSH): the *shellconfig* folders contain multiple files that can easily be
  customized
* Dynamic dotfiles: checks for applications are performed before setting up any aliases/functions
* Automated prompt customization: the Starship prompt is automatically installed and, if using TMUX, all plugins are
  automatically installed. VIM/Neovim plugins are also automatically installed
* Remote session detection: certain things will not be enabled when a SSH session is detected (for servers). Also, the
  dotfiles will not be loaded at all when a non-interactive session is opened (ex.: SFTP connection)
* Non bloated shell config: although the files are quite big, not a single alias/function/variable will be set if it is
  useless on the system (ex.: alias to an application that is not installed)
* Quick discharge: an alias called either *bbash* or *zzsh* (depending on your $SHELL) is present to quickly open a
  session without any of the dotfiles loaded. This is useful for testing/troubleshooting using a vanilla shell environment. The same thing can be applied for some applications (ex.: *vvim* to load VIM/Neovim without any configuration)

<u>**Note**</u>: these dotfiles work on both macOS (up until Catalina) and Linux. There is a somewhat compatibility with WSL2 but don't expect for everything to work out of the box.

In its current state, my $SHELL loads quite quickly with the following statistics:

```
BASH:
# time bash -i -c "echo -n"
bash -i -c "echo -n"  0.02s user 0.01s system 103% cpu 0.031 total
bash -i -c "echo -n"  0.03s user 0.01s system 102% cpu 0.038 total
bash -i -c "echo -n"  0.04s user 0.01s system 103% cpu 0.049 total
bash -i -c "echo -n"  0.03s user 0.01s system 103% cpu 0.037 total

ZSH:
# time zsh -i -c "print -n"
zsh -i -c "print -n"  0.33s user 0.10s system 103% cpu 0.416 total
zsh -i -c "print -n"  0.17s user 0.04s system 106% cpu 0.194 total
zsh -i -c "print -n"  0.17s user 0.05s system 106% cpu 0.201 total
zsh -i -c "print -n"  0.15s user 0.07s system 106% cpu 0.207 total
```


# Installation
It is possible to simply clone this repository and use the dotfiles (symlinks or copy the files):

```
git clone https://github.com/GSquad934/dotfiles.git "$HOME"/.dotfiles
```

It is necessary to modify either the *.bashrc* or the *.zshrc* file and change the following variables according to your needs:
* **DOTFILES**: defines the default location of the dotfiles ($HOME/.dotfiles).
* **SCRIPTS**: defines the default location of the custom scripts ($HOME/.local/bin)
* **SOURCES**: defines the default location of source files ($HOME/.sources)
* **REPOS**: defines the default location of git repositories ($HOME/.sources/repos)

The installation can also be automated when using my [bootstrap script](https://github.com/GSquad934/bootstrap.git)

# Miscellaneous/Comments

### Alacritty
Alacritty is rendering fonts differently depending on the screen resolution. Therefore, multiple Alacritty config files are available for my different computers.

### TMUX
TMUX configuration has changed over the years and multiple TMUX config files are available. A single one is present for my workstations and two are aimed for remote SSH connections. The file called *tmux24-server.conf* is meant to be used on servers with TMUX v2.9 or higher (earlier versions should use the file called *tmuxpre29-server.conf* for compatibility purposes).

### Weechat
Some plugins are installed for Weechat and they sometimes fail to launch when running Weechat for the first time. In such a case, it means the dotfiles here are outdated. Reinstalling the plugins fixes the issue (with the "/script" command).

### X11
The configuration files stored in *config/X11* are meant to be used only with window managers. Desktop environments come with their own *xinitrc* file anyway.

# Contact
You can always reach out to me:

* [Twitter](https://twitter.com/gaetanict)
* [Email](mailto:gaetan@ictpourtous.com)

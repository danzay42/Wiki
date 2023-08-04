
https://command-not-found.com/

# POSIX System
---

- uname
- lsblk | lscpu | lspci | lsusb | ...
- whereis | which
- cal | date

## Files
- cat | tac | split -> [bat](https://github.com/sharkdp/bat)
- head | tail | cut
- grep -> [rg](https://github.com/BurntSushi/ripgrep) -> [batgrep](https://github.com/eth-p/bat-extras/blob/master/doc/batgrep.md)
- diff | cmp -> [difft](https://github.com/Wilfred/difftastic) -> [batdiff](https://github.com/eth-p/bat-extras/blob/master/doc/batdiff.md)
- wc
- sed -> awk
- touch | cp | mv | rm | mkdir | rmdir
- echo | printf

## File System
- find -> [fd](https://github.com/sharkdp/fd)
- ls -> [exa](https://github.com/ogham/exa) | [lsd](https://github.com/lsd-rs/lsd)
- tree -> [broot](https://github.com/Canop/broot)
- [mc](https://midnight-commander.org/wiki)
- cd -> zoxide

## Permissions
- su -> doas -> sudo
- chmod | chown | chgrp

## Processes
- kill | killall
- ps -> [procs](https://github.com/dalance/procs)
- top -> htop -> [btm](https://github.com/ClementTsang/bottom)
- nvtop
- [mprocs](https://github.com/pvolok/mprocs)

## Power
- powertop
- s-tui
- [tlp & tlp-rdw](https://linrunner.de/tlp/index.html)
- [auto-cpufreq](https://github.com/AdnanHodzic/auto-cpufreq)

## Disk
- du -> [dust](https://github.com/bootandy/dust)
- df -> [dysk](https://github.com/Canop/dysk)
- gparted

## Network
- wget -> curl -> [httpie](https://httpie.io/docs/cli/main-features)
- ping
- nslookup
- nc (netcat)
- dig -> [dog](https://github.com/ogham/dog)
### Managers
- network manager (nmtui)
- wpa_supplicant
- iwd

## Super Search
- fzf -> dmenu -> [rofi](https://github.com/davatorium/rofi)

## Docs
- man | less -> info -> [batman](https://github.com/eth-p/bat-extras/blob/master/doc/batman.md)
- tldr


# Programming
---

- [tokei](https://github.com/XAMPPRocky/tokei)

## Benchmark
- time -> [hyperfine](https://github.com/sharkdp/hyperfine)

## [Git](https://git-scm.com/book/en/v2)
- [lazygit](https://github.com/jesseduffield/lazygit)
- [gitui](https://github.com/extrawurst/gitui)

## Bash
- xargs
- seq
- shuf
- test

## Python
- ipython
- bpython

## Rust
- irust
- [Evcxr](https://github.com/evcxr/evcxr)
- cargo-info


# Tiling window manager
---

- [i3](https://i3wm.org/)
- [qtile](https://qtile.org/) (python)
- awesome
- leftwm (rust)

## Compositor
- xcompmgr
- picom

## Monitor
- xrandr

## Status Bar
- **polybar**
- xmobar

## Wallpapers
- nitrogen
- **feh**

## Screenshots
- **flameshot**
- scrot

## Sound Server
- PulseAudio
- **PipeWire**

## Volume Control
- amixer

## Keyboard Layout
- setxkbmap

## Brightness
- light
- clight

## Notify
- dunst


# Soft
---

- pass
- qbittorrent
- [entr](https://github.com/clibs/entr) (event notify test runner)
- [bat-extras](https://github.com/eth-p/bat-extras/tree/master)
- atuin (best serch for command history)
- eva (calculator)

## Terminal
- sh -> bash -> zsh -> [fish](https://fishshell.com/)
- [alacritty](https://github.com/alacritty/alacritty) | kitty
- *Prompt*
	- [starship](https://starship.rs/)
- *Tabs multiplexer*
	- tmux
	- zellif
- tput
- history

## Text Editor (VI)
- nano -> vi -> vim -> [nvim](https://neovim.io/)

### Plugins & utils:
- LSP
- tree-sitter (быстрый и правильный способо подстветки кода)
- Tagbar (навигация внутри файла)
- NERDTree
- Telescope (use: ripgrep, fzf)
- [AstroNvim](https://astronvim.github.io/)

### Configs
- [kickstart](https://github.com/nvim-lua/kickstart.nvim)
- [NvChad](https://nvchad.com/)
- [LunarVim](https://www.lunarvim.org/)
- [AstroNvim](https://astronvim.github.io/)

### Troubleshooting
on Wayland install wl-clipboard
[Nerd Fonts](https://github.com/ryanoasis/nerd-fonts)
```shell
git clone --depth 1 https://github.com/ryanoasis/nerd-fonts.git
cd nerd-fonts
./install.sh
cd ../
rm -rf nerd-fonts
```


# Configs
---

## Gnome
```shell
gsettings set org.gnome.desktop.interface color-scheme prefer-dark
gsettings set org.gnome.desktop.interface enable-hot-corners false

gsettings set org.gnome.desktop.session idle-delay 1800
gsettings set org.gnome.settings-daemon.plugins.power power-button-action "interactive"
gsettings set org.gnome.settings-daemon.plugins.power sleep-inactive-battery-timeout 1200
gsettings set org.gnome.settings-daemon.plugins.power sleep-inactive-ac-type 1200

shortcut_gset=org.gnome.settings-daemon.plugins.media-keys
shortcut_custom=/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom0/

gsettings set ${shortcut_gset}.custom-keybinding:${shortcut_custom} binding '<Super>Return'
gsettings set ${shortcut_gset}.custom-keybinding:${shortcut_custom} name 'Terminal'
gsettings set ${shortcut_gset}.custom-keybinding:${shortcut_custom} command 'alacritty'
gsettings set ${shortcut_gset} custom-keybindings "['${shortcut_custom}']"

gsettings set org.gnome.desktop.input-sources per-window true
gsettings set org.gnome.desktop.input-sources sources "[('xkb', 'us'), ('xkb', 'ru')]"
```

### Extensions
- [Dash to Dock](https://github.com/micheleg/dash-to-dock)
- [Vitals](https://github.com/corecoding/Vitals)
- [AppIndicator and KStatusNotifireItem](https://github.com/ubuntu/gnome-shell-extension-appindicator)
- [Removable Drive Menu](https://gitlab.gnome.org/GNOME/gnome-shell-extensions)
- [Clipboard Indicator](https://github.com/Tudmotu/gnome-shell-extension-clipboard-indicator)
```shell
gnome-extensions enable clipboard-indicator@tudmotu.com
gnome-extensions enable appindicatorsupport@rgcjonas.gmail.com
gnome-extensions enable Vitals@CoreCoding.com
gnome-extensions enable dash-to-dock@micxgx.gmail.com
gnome-extensions enable drive-menu@gnome-shell-extensions.gcampax.github.com
```

## Locale
```shell
sudo echo "ru_RU.UTF-8 UTF-8" >> /etc/locale.gen
sudo locale-gen
```

## Misc USB visibility
`sudo usermod -aG dialout $USER`

## Arch

### Bluetooth
```shell
sudo systemctl enable bluetooth.service
sudo systemctl start bluetooth.service
```

### Sound & Microphone
[Advanced Linux Sound Architecture/Troubleshooting](https://wiki.archlinux.org/title/Advanced_Linux_Sound_Architecture)
```shell
sudo pacman -S sof-firmware
```

### Fonts
```shell
sudo pacman -S noto-fonts
```

### NVIDIA
```shell
sudo pacman -S nvidia
```
or for `geforce gtx 780m`
```shell
yay -S nvidia-470xx-dkms
```

### yay AUR Helper
```shell
sudo pacman -S --needed base-devel
git clone https://aur.archlinux.org/yay-git.git
cd yay-git
makepkg -si
```

### Gnome
```shell
sudo pacman -S gnome-themes-extra
yay -S gnome-browser-connector
sudo pacman -R gnome-boxes cheese gnome-contacts gnome-maps gnome-photos gnome-music totem gnome-weather epiphany
```

## Fedora

[rpm fusion](https://rpmfusion.org/)
```shell
sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel

sudo dnf install lame\* --exclude=lame-devel
sudo dnf group upgrade --with-optional Multimedia
```

### DNF
Edit `/etc/dnf/dnf.conf`
```
skip_if_unavailable=True
fastestmirror=True
max_parallel_downloads=10
defaultyes=True
```

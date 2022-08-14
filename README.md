# New Laptop - Arch3
## Wayland and Pipewire



### Applications + Dependencies (install with aur helper)

#### Essential Arch System Stuff (just notes for installations)
- Processor Microcode \| `amd-ucode`
- grub \| `grub efibootmgr`
- linux \| `linux linux-firmware`
- nano \| `nano nano-syntax-highlighting`
- NetworkManager \| `networkmanager`
- sudo \| `sudo`
- zsh \| `zsh`
    - oh-my-zsh, plugins and themes

#### Desktop Environment Stuff
- hyprland \| `hyprland-git`
- Alacritty \| `alacritty`
- copyQ \| `copyq`
- pipewire \| `pipewire lib32-pipewire pipewire-alsa pipewire-pulse pipewire-jack`
- pavucontrol \| `pavucontrol`
- xdg-user-dirs \| `xdg-user-dirs`

#### System Utilities (mainly terminal)
- bat \| `bat`
- cronie \| `cronie`
    - `*/15 * * * * source ~/.uservar && ~/.scripts/set-wallpaper $ZIP_CODE_COUNTRY_CODE $OWM_APIKEY` 
- duf \| `duf`
- exa \| `exa`
- fd \| `fd`
- fzf \| `fzf`
- delta \| `git-delta`
- httpie \| `httpie`
- jq \| `jq`
- man \| `man`
- nodejs \| `nodejs nvm`
- openssh \| `openssh`
- unzip \| `unzip`

#### Applications
- discord \| `discord`
- firefox \| `firefox`
- tetrio \| `tetrio-desktop`
- Visual Studio Code \| `visual-studio-code-bin`

#### Extra Stuff
- cbonsai \| `cbonsai`
- cheat \| `cheat`
- bottom \| `bottom`
- bashtop \| `bashtop`
- bandwhich \| `bandwhich`
- neofetch \| `neofetch`
- onefetch \| `onefetch`
- thefuck \| `thefuck`
- youtube-dl \| `youtube-dl`






#### other todo reference:
- lightdm
- lightdm-webkit-theme-aether
    - `sudo cp -r ~/.wallpapers /usr/share/lightdm-webkit/themes/lightdm-webkit-theme-aether/src/img/wallpapers`
- rsync
- gnome-keyring
- brightnessctl
- visual-studio-code-bin
- redshift
- polybar
- feh
- gimp
- noto-fonts, noto-fonts-cjk noto-fonts-emoji noto-fonts-extra
- imagemagick
- betterlockscreen
    - `sudo ln -sf ~/.config/betterlockscreen@.service /usr/lib/systemd/system/betterlockscreen@.service`
- lxpolkit-gtk3, polkit
- mpd, ncmpcpp, mpv
- rofi
- networkmanager-applet networkmanager-openvpn networkmanager-dmenu
    - go to protonvpn or something and download config for ovpn then add that to nm-applet and then add ovpn username and password in the extra options 
- tlp, tlp-rdw, xfce4-power-manager
- oblogout
    - `sudo ln ~/.config/oblogout.conf /etc/oblogout.conf`
- blueman
- maim
- thunar, thunar-archive-plugin, thunar-media-tags-plugin, thunar-volman
- wtfutil
- oneko
- phinger-cursors

other installations:
 - oh-my-zsh
    - zsh-autosuggestions
    - zsh-completions
    - zsh-syntax-highlighting
    - powerline10k
 - tor-browser (from site)
 - [Anime4K](https://github.com/bloc97/Anime4K/blob/master/md/GLSL_Instructions_Linux.md)
 - [Steam](https://wiki.archlinux.org/title/Steam)


.uservar (secret env variables)
- $OWM_API_KEY
- $ZIP_CODE_COUNTRY_CODE

todo [Arch Desktop Environment](https://wiki.archlinux.org/title/desktop_environment#Custom_environments):
- [x] Display Server - ~~Xorg~~ Wayland
- [x] Window Compositor - ~~jonaburg/picom~~ Hyprland
- [ ] Display Manager - lightdm + aether
- [ ] Screen Locker - betterlockscreen
    - [ ] Core i3lock-color options?
- [ ] Application Launcher - rofi
    - [ ] Themeing
    - [ ] ~~Openbox Keybinds~~
- [ ] Notification Daemon - dunst
    - [ ] Themeing
    - [ ] Extra Functionality
- [x] Audio control - Pulseaudio
    - [ ] Connect to notifications
    - [ ] ~~Openbox Keybinds~~
- [ ] Backlight control - brightnessctl, redshift
    - [ ] connect to notifications
- [ ] Media control - mpd, ncmpcpp, mpv
    - [ ] ~~Openbox Keybinds - playerctl?~~
    - [ ] Connect to notifications
- [ ] Panel/bar - polybar
    - [ ] Themeing and functionality
- [ ] Polkit - lxpolkit-gtk3
- [ ] Power Management - tlp, tlp-rdw, xfce4-power-manager
- [ ] Screen capture - maim
    - [ ] ~~Openbox Keybinds~~
    - [ ] Connect to notifications
    - [ ] Extra Functionality (save to clipboard)
- [ ] Clipboard Management - ~~clipcat~~ CopyQ
- [ ] Wallpaper Setter - feh
    - [x] React to weather and time
- [ ] Logout Dialogue - oblogout (replace with rofi?)
    - [ ] Themeing
    - [ ] Keybind
- [x] Default Applications
    - [ ] IDE - VS Code
        - [ ] Custom Theme?
    - [x] Term - Alacritty + zsh + oh-my-zsh
    - [ ] File Manager - thunar, thunar-archive-plugin, thunar-media-tags-plugin, thunar-volman
        - [ ] Themeing + Extra Functionality
    - [ ] Photo Editor - gimp
    - [x] Web browser - firefox ( hope to change later with more custom browser )
- [ ] Sidebar Widgets - eww
- [ ] ~~Window Manager - openbox~~
- [ ] Bluetooth - blueman
- [ ] Misc.
    - [ ] Gtk2/3 Themeing - oomox/themix

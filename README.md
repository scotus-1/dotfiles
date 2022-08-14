# New Laptop - Arch3
#### Wayland and Pipewire



applications + dependencies (install with aur helper)
- alacritty
- firefox
- lightdm
- lightdm-webkit-theme-aether
    - `sudo cp -r ~/.wallpapers /usr/share/lightdm-webkit/themes/lightdm-webkit-theme-aether/src/img/wallpapers`
- openbox
- openssh
- ttf-dejavu
- ttf-liberation
- rsync
- thefuck
- xorg-server, xorg-xinput
- zsh
- gnome-keyring
- bottom
- brightnessctl
- visual-studio-code-bin
- nano-syntax-highlighting
- neofetch
- discord
- redshift
- bat, exa, fd, cheat
- alsa-utils
- pulseaudio, pulseaudio-alsa, pulseaudio-bluetooth
- polybar
- jq, httpie
- feh
- cronie
    - `*/15 * * * * source ~/.uservar && ~/.scripts/set-wallpaper $ZIP_CODE_COUNTRY_CODE $OWM_APIKEY`
- gimp
- onefetch
- noto-fonts, noto-fonts-cjk noto-fonts-emoji noto-fonts-extra
- youtube-dl
- tetrio
- lua
- arch-wiki-docs arch-wiki-lite dialog 
- xorg-xrandr psmisc xorg-xrdb
- imagemagick
- betterlockscreen
    - `sudo ln -sf ~/.config/betterlockscreen@.service /usr/lib/systemd/system/betterlockscreen@.service`
- cbonsai
- unzip
- lxpolkit-gtk3, polkit
- picom-jonaburg-git
- mpd, ncmpcpp, mpv
- rofi
- bashtop
- zentile
- networkmanager-applet networkmanager-openvpn networkmanager-dmenu
    - go to protonvpn or something and download config for ovpn then add that to nm-applet and then add ovpn username and password in the extra options 
- tlp, tlp-rdw, xfce4-power-manager
- clipcat
- git-delta
- oblogout
    - `sudo ln ~/.config/oblogout.conf /etc/oblogout.conf`
- blueman
- maim
- thunar, thunar-archive-plugin, thunar-media-tags-plugin, thunar-volman
- duf, bandwhich, fzf, lazygit
- atom, nvm
    - `nvm install node`
- wtfutil
- oneko
- phinger-cursors
other installations:
 - oh-my-zsh
    - zsh-autosuggestions
    - zsh-completions
    - zsh-syntax-highlighting
    - powerline10k
 - toipe (cargo)
 - tor-browser (from site)
 - [Anime4K](https://github.com/bloc97/Anime4K/blob/master/md/GLSL_Instructions_Linux.md)
 - [Steam](https://wiki.archlinux.org/title/Steam)


.uservar (secret env variables)
- $OWM_API_KEY
- $ZIP_CODE_COUNTRY_CODE

todo [Arch Desktop Environment](https://wiki.archlinux.org/title/desktop_environment#Custom_environments):
- [x] Display Server - ~~Xorg~~ Wayland
- [x] Window Compositor - ~~jonaburg/picom~~ HyprLand
- [ ] Display Manager - lightdm + aether
- [ ] Screen Locker - betterlockscreen
    - [ ] Core i3lock-color options?
- [ ] Application Launcher - rofi
    - [ ] Themeing
    - [ ] ~~Openbox Keybinds~~
- [ ] Notification Daemon - dunst
    - [ ] Themeing
    - [ ] Extra Functionality
- [x] Audio control - ~~pulseaudio, pulseaudio-alsa, alsa-utils, pulseaudio-bluetooth~~ pipewire pipewire-alsa pipewire-pulse pipewire-jack
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
- [ ] Clipboard Management - clipcat
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

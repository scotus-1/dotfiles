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
- xorg-server
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
- pulseaudio, pulseaudio-alsa
- polybar
- jq, httpie
- feh
- cronie
    - `*/15 * * * * ~/.scripts/set-wallpaper $ZIP_CODE_COUNTRY_CODE $OWM_APIKEY`
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


other installations:
 - oh-my-zsh
    - zsh-autosuggestions
    - zsh-completions
    - zsh-syntax-highlighting
    - powerline10k
 - toipe (cargo)
 - tor-browser (from site)

.uservar (secret env variables)
- $OWM_API_KEY
- $ZIP_CODE_COUNTRY_CODE

todo:
- [x] Display Server - Xorg
- [ ] Window Compositor - picom (fork? jonaburg)
- [x] Display Manager - lightdm + aether
- [x] Screen Locker - betterlockscreen
    - [ ] more i3lock-color options?
- [ ] Application Launcher - rofi
- [ ] Notification Launcher - dunst
- [x] Audio control - pulseaudio, pulseaudio-alsa, alsa-utils
    - [ ] connect to notifications
- [x] Backlight control - brightnessctl, redshift
    - [ ] connect to notifications
- [ ] Media control - (mpd, mpv, vlc ?????? playerctl?)
- [ ] Panel/bar - polybar
- [ ] Polkit - ???
- [ ] Power Management - ???
- [ ] Screen capture - ???
- [ ] Clipboard Management - ???
- [x] Wallpaper Setter - feh
    - [x] React to weather and time
- [ ] Logout Dialogue - ???
- [ ] Default Applications
    - [x] IDE - VS Code
    - [x] Term - Alacritty + zsh + oh-my-zsh
    - [ ] File Manager - ???
    - [x] Photo Editor - gimp
    - [x] Web browser - firefox ( hope to change later with more custom browser )
- [ ] Sidebar Widgets - eww
- [x] Window Manager - openbox
    - [ ] Themeing
    - [ ] Other configurations (keybinds, applications, rc.xml)

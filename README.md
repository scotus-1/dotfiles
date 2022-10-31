# New Laptop - Arch3
## Wayland and Pipewire



### Applications + Dependencies (install with aur helper)

#### Essential Arch System Stuff (just notes for installations)
- Processor Microcode \| `amd-ucode` or other microcode packages
- grub \| `grub efibootmgr`
    - grub installation and make config for grub
- linux \| `linux-zen linux-firmware`
    - Enable color and ILoveCandy in /etc/pacman.conf
- nano \| `nano nano-syntax-highlighting`
- NetworkManager \| `networkmanager`
    - [Edit /etc/hosts](https://wiki.archlinux.org/title/Network_configuration#localhost_is_resolved_over_the_network)
    - `systemctl enable NetworkManager`
- sudo \| `sudo`
    - `echo "%wheel ALL=(ALL) ALL" >> /etc/sudoers` 
- zsh \| `zsh`
    - oh-my-zsh, plugins and themes
    ```zsh
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    gcl $gh/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    gcl $gh/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    gcl $gh/zsh-users/zsh-completions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-completions
    gcl --depth=1 $gh/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
    ```
- lxqt-policykit \| `lxqt-policykit polkit`
- fprint \| `fprintd`
    ```zsh
    for finger in {left,right}-{thumb,{index,middle}-finger}; do fprintd-enroll -f "$finger" "$USER"; done
    ```
- Add user \| `useradd -m $user; passwd $user; usermod -aG wheel,audio,video,optical,storage $user`
- Install yay
    ```zsh
    sudo pacman -S --needed git base-devel
    git clone https://aur.aurchlinux.org/yay.git
    cd yay
    makepkg -si
    ```


#### Desktop Environment Stuff
- hyprland \| `hyprland-git`
- Alacritty \| `alacritty`
- copyQ \| `copyq`
- pipewire \| `pipewire lib32-pipewire pipewire-alsa pipewire-pulse pipewire-jack`
- pavucontrol \| `pavucontrol`
- xdg-user-dirs \| `xdg-user-dirs`
    - `xdg-user-dirs-update`
- SDDM \| `sddm-git plasma-framework`
    ```zsh
    sudo mkdir /etc/sddm.conf.d
    sudo mv /usr/lib/sddm/sddm.conf.d/default.conf /etc/sddm.conf.d/default.conf
    sudo cp -r sweet/ /usr/share/sddm/themes 
    ```
    - Edit default.conf and change to `Current=Sweet` in `[Theme]`
- blueman \| `blueman`
    - `sudo systemctl enable bluetooth.service --now`
- waybar \| `waybar`
- mpd \| `mpd`
    - `systemctl enable mpd.service --user --now`
- ttf-ms-fonts \| `ttf-ms-fonts`
- noto-fonts \| `noto-fonts noto-fonts-cjk noto-fonts-emoji noto-fonts-extra`

#### System Utilities (mainly terminal)
- bat \| `bat`
- cronie \| `cronie`
    - `sudo systemctl enable cronie.service`
    - `crontab -e`
    - `*/15 * * * * export WAYLAND_DISPLAY=wayland-0; ~/.scripts/set-wallpaper` 
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
- gping \| `gping`
- rsync \| `rsync`


#### Applications
- discord \| `discord`
- firefox \| `firefox`
- tetrio \| `tetrio-desktop`
- Visual Studio Code \| `visual-studio-code-bin`
- [Waydroid](https://wiki.archlinux.org/title/Waydroid#Installation) \| `waydroid`
- mpv \| `mpv`
- ncmpcpp \| `ncmpcpp`

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
- sl \| `sl`
- tldr  \| `tldr`


#### other todo reference:
- redshift
- feh
- gimp
- noto-fonts, noto-fonts-cjk noto-fonts-emoji noto-fonts-extra
- imagemagick
- betterlockscreen
    - `sudo ln -sf ~/.config/betterlockscreen@.service /usr/lib/systemd/system/betterlockscreen@.service`
- networkmanager-applet networkmanager-openvpn networkmanager-dmenu
    - go to protonvpn or something and download config for ovpn then add that to nm-applet and then add ovpn username and password in the extra options 
- tlp, tlp-rdw, xfce4-power-manager
- oblogout
    - `sudo ln ~/.config/oblogout.conf /etc/oblogout.conf`
- maim
- thunar, thunar-archive-plugin, thunar-media-tags-plugin, thunar-volman
- phinger-cursors

#### Other Installations:
 - [Anime4K](https://github.com/bloc97/Anime4K/blob/master/md/GLSL_Instructions_Linux.md)
 - [Steam](https://wiki.archlinux.org/title/Steam)

#### .uservar (secret env. variables)
- OWM_API_KEY=api_key
- ZIP_CODE_COUNTRY_CODE=zipcode,country

#### Todo [Arch Desktop Environment](https://wiki.archlinux.org/title/desktop_environment#Custom_environments):
- [x] Display Server - ~~Xorg~~ \| Wayland
- [x] Window Compositor - ~~jonaburg/picom~~ \| Hyprland
- [x] Display Manager - ~~lightdm + aether~~ \| SDDM
- [ ] Screen Locker - betterlockscreen
    - [ ] Core i3lock-color options?
- [ ] Application Launcher - rofi
    - [ ] Themeing
    - [ ] ~~Openbox Keybinds~~
- [ ] Notification Daemon - dunst
    - [ ] Themeing
    - [ ] Extra Functionality
- [x] Audio control - Pipewire
    - [ ] Connect to notifications
    - [ ] ~~Openbox Keybinds~~
- [ ] Backlight control - brightnessctl, redshift
    - [ ] connect to notifications
- [x] Media control - mpd, ncmpcpp, mpv
    - [ ] ~~Openbox Keybinds - playerctl?~~
    - [ ] Connect to notifications
- [x] Panel/bar - ~~polybar~~ \| waybar
    - [ ] Themeing and functionality
- [x] Polkit - lxqt-policykit
- [ ] Power Management - tlp, tlp-rdw, xfce4-power-manager
- [ ] Screen capture - maim
    - [ ] ~~Openbox Keybinds~~
    - [ ] Connect to notifications
    - [ ] Extra Functionality (save to clipboard)
- [x] Clipboard Management - ~~clipcat~~ CopyQ
- [x] Wallpaper Setter - swaybg
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
- [x] Bluetooth - blueman
- [ ] Misc.
    - [ ] Gtk2/3 Themeing - oomox/themix


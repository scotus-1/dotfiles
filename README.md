# ~~New Laptop~~ THE REBOOT - Arch4
## Wayland and Pipewire



### Applications + Dependencies (Install with AUR helper)

#### Essential Arch System Stuff (just notes for installations)
- Processor Microcode \| `amd-ucode` or other microcode packages
- linux \| `linux-zen linux-firmware`
    - Enable Color and ILoveCandy + multilib  in /etc/pacman.conf
- grub \| `grub efibootmgr`
    ```zsh
    grub-install --target=x86_64-efi --efi-directory=esp --bootloader-id=GRUB
    grub-mkconfig -o /boot/grub/grub.cfg
    ```
- nano \| `nano nano-syntax-highlighting`
- man \| `man`
- NetworkManager \| `networkmanager`
    - [Edit /etc/hosts](https://wiki.archlinux.org/title/Network_configuration#localhost_is_resolved_over_the_network)
    - `systemctl enable NetworkManager`
- sudo \| `sudo`
    - `echo "%wheel ALL=(ALL) ALL" >> /etc/sudoers` 
- Add user (after arch-chroot) \| `useradd -m $user; passwd $user; usermod -aG wheel,audio,video,optical,storage $user`
- **Reboot**
- zsh \| `zsh`
    ```zsh
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    gcl $gh/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    gcl $gh/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    gcl $gh/zsh-users/zsh-completions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-completions
    gcl --depth=1 $gh/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
    rm .bash_history .bash_logout .bash_profile .bashrc .shell.pre-oh-my-zsh
    mv .zshrc.pre-oh-my-zsh .zshrc
    zsh
    ```
- Install yay \| `git base-devel`
    ```zsh
    git clone https://aur.aurchlinux.org/yay.git
    cd yay
    makepkg -si
    cd ..; rm -rf yay
    ```
- Add dotfiles and ssh/gpg \| `openssh github-cli`
    ```zsh
    gh auth login
    ssh-keygen -t ed25519 -C "$email"; ssh-add ~/.ssh/id_ed25519
    gh ssh-key add ~/.ssh/id_ed25519.pub --title $hostname
    git clone https://github.com/scotus-1/dotfiles.git
    cd dotfiles; mv .git ../.dotfiles_git; mv .* ..
    cd ..; rmdir dotfiles
    gpg --full-generate-key
    gpg --list-secret-keys --keyid-format=long
    git config --global user.signingkey $KEY
    git config --global commit.gpgsign true
    git config --global user.email "$email"
    git config --global user.name "$name"
    ```
    - Add gpg to GitHub \| `gpg --armor --export $KEYID`
- Install everything else then reboot

    
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
    sudo systemctl enable sddm.service
    sudo mkdir /etc/sddm.conf.d
    sudo mv /usr/lib/sddm/sddm.conf.d/default.conf /etc/sddm.conf.d/default.conf
    sudo cp -r .themes/sweet/ /usr/share/sddm/themes
    setfacl -m u:sddm:x ~/
    setfacl -m u:sddm:r ~/.face.icon 
    ```
    - Edit default.conf and change to `Current=sweet` in `[Theme]`
- blueman \| `blueman`
    - `sudo systemctl enable bluetooth.service --now`
- waybar \| `waybar`
- mpd \| `mpd`
    - `systemctl enable mpd.service --user --now`
- ttf-ms-fonts \| `ttf-ms-fonts`
- noto-fonts \| `noto-fonts noto-fonts-cjk noto-fonts-emoji noto-fonts-extra`
- lxqt-policykit \| `lxqt-policykit polkit`
- fprint \| `fprintd`
    ```zsh
    for finger in {left,right}-{thumb,{index,middle}-finger}; do fprintd-enroll -f "$finger" "$USER"; done
    ```


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
- gimp \| `gimp`
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
- nvm \| `nvm`


#### other todo reference:
- redshift
- feh
- imagemagick
- betterlockscreen
    - `sudo ln -sf ~/.config/betterlockscreen@.service /usr/lib/systemd/system/betterlockscreen@.service`
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


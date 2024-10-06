## Initial Installation

### Initial Steps

1. download ISO onto USB 
2. boot from USB (turn system protections off) 
3. ```iwctl --passphrase staidyrapt39813 station wlan0 connect OPTUS_F5F134```
4. ```archinstall```

### Configuration

- mirror region - australia
- locales - colemak, en_AU, UTF-8
- disk configuration - partitioning -> best-effort -> ext4 -> yes 
- set root and user password
- profile - install WM
- audio - pipewire
- kernels - add linux-lts
- network configuration - use NM
- timezone - NSW

reboot after done (do not chroot)

connecting to wifi again:
```
nmtui
```

## Downloading Packages

### Basic Packages

git 
```
sudo pacman -Syu 

sudo pacman -S --needed base-devel git
```

yay (package manager) (CHECK DIRECTORY)
```
git clone https://aur.archlinux.org/yay.git

cd yay

makepkg -si
```

dolphin (file manager) 
```
sudo pacman -S dolphin
```

waybar
```
sudo pacman -S waybar
```

rofi (must be wayland fork)
```
yay -S rofi-lbonn-wayland-git
```

firefox 
```
yay -S firefox
```


### Setting up Bluetooth and Sound

https://www.jeremymorgan.com/tutorials/linux/how-to-bluetooth-arch-linux/

```
sudo pacman -S bluez bluez-utils blueman
```

make sure btusb is running:
```
lsmod | grep btusb
```

allow autoenable:
```
sudo vim /etc/bluetooth/main.conf

AutoEnable=true
```

start the service and enable it automatically:
```
sudo systemctl start bluetooth.service

sudo systemctl enable bluetooth.service
```

to run bluetooth interface:
```
blueman-manager
```

```
sudo pacman -S pavucontrol
```

### Fonts
```
yay -S noto-fonts-cjk

yay -S ttf-font-awesome

yay -S nerd-fonts

yay -S ttf-jetbrains-mono ttf-jetbrains-mono-nerd

yay -S ttf-roboto-mono ttf-roboto-mono-nerd
```

### Apps

onedrive 
```
yay -S pamac

pamac build onedrive-abraunegg
```

obsidian 
```
yay -S obsidian
```

vscode 
```
yay -S visual-studio-code-bin
```

spotify
```
yay -S spotify-launcher

yay -S spicetify-cli
```

### Lock and Logout

wlogout
```
yay -S wlogout
```

hyprlock 
```
yay -S hyprlock
```

### Wallpaper

swaybg
```
sudo pacman -S swaybg
```

### Miscellaneous

unzip
```
sudo pacman -S unzip

unzip /path.zip
```

hyprshot
```
yay -S hyprshot
```

hyprpicker
```
yay -S hyprpicker-git
```

neofetch 
```
sudo pacman -S neofetch
```

cmatrix 
```
sudo pacman -S cmatrix
```

btop
```
sudo pacman -S btop
```

ranger
```
sudo pacman -S ranger
```


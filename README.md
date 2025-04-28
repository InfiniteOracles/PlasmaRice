# PlasmaRice
Documentation for installing my Plasma KDE rice setup.

---

## Wallpaper

- Source: [dharmx/walls](https://github.com/dharmx/walls/tree/main)  
- Wallpaper used: [Snowy Mountain Tops](https://github.com/dharmx/walls/blob/main/nord/a_snowy_mountain_tops.jpg)

---

## Terminal Setup

- **Terminal:** Alacritty
- **Shell:** Fish
- **Prompt Theme:** Oh My Posh [Dracula ](https://draculatheme.com/oh-my-posh)

### Install / Configure Instructions (Terminal)

```bash
yay -S alacritty
yay -S fish
yay -S oh-my-posh
```

### Set Fish as Default Shell
> You must reboot for this to take effect.

```bash
chsh -s /usr/bin/fish
```

### Remove Fish Welcome Message

```bash
set -U fish_greeting ""
```

### Auto-launch Neofetch and Oh My Posh

Edit your `config.fish` file:

```bash
nano ~/.config/fish/config.fish
```

Inside the `if status is-interactive` block, add:

```bash
neofetch
oh-my-posh init fish --config {path-to-config}.json | source
```
*(replace `{path-to-config}` with your actual Oh My Posh config path)*

---

## Application Launcher Setup

- **Launcher:** Rofi with Dracula theme  
  [Dracula Rofi Theme](https://github.com/dracula/rofi)

### Install Rofi

```bash
yay -S rofi
```

Edit the Rofi config:

```bash
sudo nano /etc/rofi.rasi
```

Replace the contents with the Dracula `.rasi` config.

### Add Shortcut for Rofi
1. Open **KDE Settings** → **Shortcuts**.
2. Add a new **Custom Command**:
   - Command:
     ```bash
     rofi -normal-window -show run
     ```
   - Set a hotkey for it.

> `-normal-window` fixes bugs where you can't type (in KDE Plasma).

---

## KDE Taskbar Removal

1. Right-click the desktop and enter **Edit Mode**.
2. Click the taskbar and select **Remove**.

> This will make it so you only use Rofi.  
> To switch windows, use **Alt + Tab**.

---

## Neofetch Config

- Source: [Chick2D/neofetch-themes](https://github.com/Chick2D/neofetch-themes)  
- Config used: [talljoe.conf](https://github.com/chick2d/neofetch-themes/blob/main/normal/talljoe.conf)

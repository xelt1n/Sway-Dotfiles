# Sway Dotfiles

![License](https://img.shields.io/badge/license-MIT-green)
![WM](https://img.shields.io/badge/WM-Sway-blue)

Minimal Sway setup with, no animations, and a clean Waybar. Built for low-power or older hardware — no compositor effects, VRR disabled, GPU modifiers stripped.

---

## Stack

| Role | Tool |
|---|---|
| Window manager | Sway |
| Bar | Waybar |
| Launcher / menus | Wofi + wmenu |
| Terminal | Foot |
| Audio | PipeWire / PulseAudio |
| Screenshots | grim + slurp |
| Clipboard | wl-clipboard |
| Brightness | brightnessctl |

---

## Keybindings

`$mod` = Super (Win key)

### Basics

| Keybind | Action |
|---|---|
| `$mod + Return` | Open terminal (foot) |
| `$mod + d` | App launcher (wofi drun) |
| `$mod + q` | Kill focused window |
| `$mod + Shift + c` | Reload Sway config |
| `$mod + Shift + e` | Exit Sway |

### Focus & Movement

| Keybind | Action |
|---|---|
| `$mod + h/j/k/l` | Move focus left/down/up/right |
| `$mod + Arrow keys` | Move focus (arrow key variant) |
| `$mod + Shift + h/j/k/l` | Move window |
| `$mod + Shift + Arrow keys` | Move window (arrow key variant) |

### Workspaces

| Keybind | Action |
|---|---|
| `$mod + 1–0` | Switch to workspace 1–10 |
| `$mod + Shift + 1–0` | Move window to workspace 1–10 |
| `$mod + Tab` | Toggle back to previous workspace |

### Layout

| Keybind | Action |
|---|---|
| `$mod + b` | Split horizontal |
| `$mod + v` | Split vertical |
| `$mod + s` | Stacking layout |
| `$mod + w` | Tabbed layout |
| `$mod + e` | Toggle split |
| `$mod + f` | Fullscreen |
| `$mod + Shift + Space` | Toggle floating |
| `$mod + Space` | Toggle focus tiling/floating |
| `$mod + a` | Focus parent container |
| `$mod + r` | Enter resize mode |

### Scratchpad

| Keybind | Action |
|---|---|
| `$mod + Shift + -` | Send window to scratchpad |
| `$mod + -` | Cycle scratchpad windows |

### Resize mode (`$mod + r`)

| Keybind | Action |
|---|---|
| `h / Left` | Shrink width |
| `l / Right` | Grow width |
| `k / Up` | Shrink height |
| `j / Down` | Grow height |
| `Enter / Escape` | Exit resize mode |

### Media & System Keys

| Keybind | Action |
|---|---|
| `XF86AudioMute` | Toggle mute |
| `XF86AudioLowerVolume` | Volume -5% |
| `XF86AudioRaiseVolume` | Volume +5% |
| `XF86AudioMicMute` | Toggle mic mute |
| `XF86MonBrightnessDown` | Brightness -5% |
| `XF86MonBrightnessUp` | Brightness +5% |
| `Print` | Screenshot selection → `~/Pictures/Screenshots/` + clipboard |
| `Shift + Print` | Screenshot full screen → `~/Pictures/Screenshots/` + clipboard |

---

## Scripts

### Power menu (`scripts/powermenu.sh`)

Opens a Wofi dmenu with four options: Shutdown, Reboot, Suspend, Logout. Uses `loginctl` if available, falls back to raw system commands.

## Input

- **Keyboard layout:** Italian (`it`) — change in `sway/config` if needed
- **Touchpad:** tap-to-click, natural scroll, adaptive acceleration
- **Mouse:** focus follows mouse, no cursor warping

---

## Display

- VRR disabled (`adaptive_sync off`)
- `WLR_DRM_NO_MODIFIERS=1` set on startup (improves compatibility on older/integrated GPUs)
- Default scale: 1

---

## Installation

```bash
git clone https://github.com/xelt1n/Sway-Dotfiles.git
cd Sway-Dotfiles
chmod +x install.sh
./install.sh
```

The script backs up existing configs to `~/.config_backup_YYYYMMDD_HHMMSS`, installs dependencies via your distro's package manager, and copies configs into `~/.config/`.

**Supported distros:** Arch / CachyOS / Manjaro · Debian / Ubuntu / Mint / Kali · Void · Gentoo

After install, log out and select **Sway** from your login manager.

### Uninstall

```bash
chmod +x uninstall.sh
./uninstall.sh
```

---

## Post-install notes

- Put wallpapers in `~/Pictures/wallpapers/` for the wallpaper picker to work
- Screenshots save to `~/Pictures/Screenshots/` — create the folder if it doesn't exist
- Change `xkb_layout it` in `sway/config` to your keyboard layout code if not Italian
- The default wallpaper path at the top of `sway/config` (`/home/user/Wallpapers/Wallhaven.png`) needs to be updated to your actual path

---

## File structure

```
.
├── sway/
│   └── config              # Main Sway config
├── waybar/
│   ├── config              # Bar modules and layout
│   └── style.css           # Bar styling
├── wofi/
│   └── style.css           # Launcher styling
├── foot/
│   └── foot.ini            # Terminal config
├── scripts/
│   ├── powermenu.sh        # Power menu (shutdown/reboot/suspend/logout)
│   └── wallpaper-menu.sh   # Wallpaper picker
├── install.sh
└── uninstall.sh
```

---

## Credits

Forked from [DPFschermo/Sway-Dotfiles](https://github.com/DPFschermo/Sway-Dotfiles).

# 🏔️ PolyNord
> A polybar module for NordVPN to easiliy connet to the available countries and cities.

# Dependencies
- `jq` - For JSON handling
- `polybar`
- `nordvpn`
- `rofi` - To easily choose between servers

## Libraries Used
- `os`
- `sys`
- `json`
- `time`
- `socket`
- `subprocess`
- `select`
- `contextlib`

# Installation
1. First you should install the cli version of [NordVPN](https://aur.archlinux.org/packages/nordvpn-bin)
2. `groupadd -r nordvpn`, `usermod -aG nordvpn $USER` | [Arch Wiki](https://wiki.archlinux.org/title/NordVPN)
3. Enable the nordvpn.service using `systemctl enable nordvpn.service`
4. Login using `nordvpn login`, it will output a link to open on your browser
5. Clone the repo in your polybar config folder (e.g., `/home/$USER/.config/polybar/`)
6. Give exec permission to the scripts: `chmod +x vpn_menu polynord`
7. Add this module to your polybar config (modify $USER to your own user name):

```
[module/nord]
type = custom/script
exec       = /home/$USER/.config/polybar/polynord
tail       = true
label      = %output%
click-left  = /home/$USER/.config/polybar/polynord connect
click-right = /home/$USER/.config/polybar/polynord disconnect
click-middle = /home/$USER/.config/polybar/vpn_menu.sh
```

8. Add `nord` to your module section in your polybar config (e.g., modules-right, modules-center, etc)

## Usage
click-right: Automatically connects to the best server available
click-left: Disconnects
click-middle: Opens `rofi` to select countries, when you select a country, it will give you all the available cities to connect to

# ☕ Support
If you liked the project, please consider giving it a star and sharing it with other people!

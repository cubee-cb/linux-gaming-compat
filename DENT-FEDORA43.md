Testing things on an all-AMD Fedora 43 desktop.

### Shortcuts
- [Setup](#setup)
- [Perfect Games](#perfect-games)
- [Games](#games)
- [Software](#software)

---

## Setup

---

### PC Hardware
- AMD Ryzen 5 5600G (iGPU disabled)
- AMD Radeon RX 6600XT (8GB)
- 32GB RAM (2x16GB, 3600Mhz, DDR4)
- OS is on a SATA SSD.
- Most games installed on a hard drive, some on an extra NVMe, a couple on the OS drive.

### PC Software
- Distro: Fedora 43 (upgraded from Fedora 41)
- Desktop: KDE Plasma, Wayland
- Steam: Runtime (i.e. not the flatpak)
- Epic Store + GOG: Heroic Games Launcher
  - Also used as a launcher for various additional games.
- Proton: [GE-Proton9-18](https://github.com/GloriousEggroll/proton-ge-custom/releases/tag/GE-Proton9-18) (Default for all games and launchers, unless otherwise specified)
    - To install a custom Proton version, I use [ProtonUp-Qt](https://github.com/DavidoTek/ProtonUp-Qt) (in Flatpaks, look for `pupgui2`).

---

## Perfect Games
A list of games that "just work". Any issues that exist here should be small and easy to work around.

---

- Abandoned Pub (Neuro-Sama Game Jam) ([itch.io](https://pipeheads.itch.io/abandoned-pub) via Heroic)
- Bashful Adoration Demo ([itch.io](https://kittywampusgames.itch.io/bashfuladoration) via Heroic)
- Bloons TD 6 ([Steam](https://store.steampowered.com/app/960090/Bloons_TD_6/) + [Epic Store](https://store.epicgames.com/en-US/p/bloons-td-6-bf95a0) via Heroic)
- DNF Duel ([Epic Store](https://store.epicgames.com/en-US/p/dnf-duel-07d055) via Heroic)
- Rocket League ([Epic Store](https://store.epicgames.com/en-US/p/rocket-league) via Heroic)
- SM64 Co-op DX (Linux) ([GitHub](https://github.com/coop-deluxe/sm64coopdx) via Heroic)
- UNDERTALE Yellow ([Game Jolt](https://gamejolt.com/games/UndertaleYellow/136925) via Heroic)
- Unhando (Neuro-Sama Game Jam) ([itch.io](https://jwapobie.itch.io/unhando) via Heroic)

---

## Games
Games I've tested and how well they work, plus tinker steps to get them working if possible.

^ - Specified Proton version. (notes will mention what version and why)

---

### ^ Second Stellar ([Steam](https://store.steampowered.com/app/3176850/Second_Stellar/))
- Using `GE-Proton10-20-rtsp19`. (I already had this version installed for VRChat; RTSP is not needed for this game)
  - Due to an issue with "newer Unity updates" on Proton9, the mouse may not work correctly. In this case, you may be unable to actually use your weapon skills as expected. You can do one of the following:
    - Re-map things to not use the mouse buttons at all (use keyboard keys, map the mouse to keyboard keys, use a controller, etc)
    - Change your proton to a Proton10 version.
  - *Technically* you can still use the weapon skills on Proton9, you just have to hold another mouse button while you do it, which is a little awkward.

### ^ Garry's Mod ([Steam](https://store.steampowered.com/app/4000/Garrys_Mod/))
- GMod has been fairly unstable on this distro; I have ended up using the Windows build under `GE-Proton9-18` as somewhat ironically that's more stable. Specifically, if I remember correctly:
  - The default 32-bit build fails to render the webviews, so the menus don't work.
  - The 64-bit branch likes to crash and is generally unstable. Needed patches to update webview for that to even work.

### Just Cause 3 ([Steam](https://store.steampowered.com/app/225540/Just_Cause_3/))
- Works pretty much flawlessly. Clicking off the window may disable Fullscreen Mode, you will have to turn it back on in the settings.
- To skip the intro videos:
  - [How-to](https://steamcommunity.com/sharedfiles/filedetails/?id=570542665). This uses the `dropzone` folder to replace the intro video with an empty file.
  - Launch options: `gamemoderun %command% --vfs-fs dropzone --vfs-archive patch_win64 --vfs-archive archives_win64 --vfs-archive dlc_win64 --vfs-fs`

### Borderlands 3 ([Epic Store](https://store.epicgames.com/en-US/p/borderlands-3) via Heroic)
- Complains about being unable to save the settings.
  - I forgot what I did to fix it, and if the fix was consistent.

### Ghostrunner ([Epic Store](https://store.epicgames.com/en-US/p/ghostrunner) via Heroic)
- I had to install the following via Winetricks:
  - `vcrun2022`

### Modern Modern Chef ([itch.io](https://bunnynaut.itch.io/modern-modern-chef) via Heroic)
- Crashes when starting a level.

---

## Software
Software I've tested and how well they work, plus tinker steps to get them working if possible.

^ - Specified Proton version. (notes will mention what version and why)

---

### VNyan ([itch.io](https://suvidriel.itch.io/vnyan) via Heroic)
- Needs fonts installed via Winetricks to render text properly:
  - `corefonts`
- Unsure if transparency works; you may need to colour key the black background in OBS and make sure your model never uses pure black.


Testing things on an all-AMD Fedora 43 desktop.


### Shortcuts
- [Setup](#setup)
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
- Fedora 43 (initially installed as Fedora 41)
- KDE Plasma (Wayland)
- Steam (Runtime) (i.e. not the flatpak)
- Heroic Games Launcher
  - For Epic Store and GOG games, as well as a launcher for various additonal games.
- Default Proton: [GE-Proton9-18](https://github.com/GloriousEggroll/proton-ge-custom/releases/tag/GE-Proton9-18) (unless otherwise specified)
    - To install a custom Proton version, I use [ProtonUp-Qt](https://github.com/DavidoTek/ProtonUp-Qt) (in Flatpaks, look for `pupgui2`).

---

## Games
Games I've tested and how well they work, plus tinker steps to get them working if possible.

^ - Specified Proton version. (notes will mention what version and why)

---

### ^ [Second Stellar](https://store.steampowered.com/app/3176850/Second_Stellar/)
- Using `GE-Proton10-20-rtsp19`. (I already had this version installed for VRChat; RTSP is not needed for this game)
  - Due to an issue with "newer Unity updates" on Proton9, the mouse may not work correctly. In this case, you may be unable to actually use your weapon skills as expected. You can do one of the following:
    - Re-map things to not use the mouse buttons at all (use keyboard keys, map the mouse to keyboard keys, use a controller, etc)
    - Change your proton to a Proton10 version.
  - *Technically* you can still use the weapon skills on Proton9, you just have to hold another mouse button while you do it, which is a little awkward.

### ^ [Garry's Mod](https://store.steampowered.com/app/4000/Garrys_Mod/)
- GMod has been fairly unstable on this distro; I have ended up using the Windows build under `GE-Proton9-18` as somewhat ironically that's more stable. Specifically, if I remember correctly:
  - The default 32-bit build fails to render the webviews, so the menus don't work.
  - The 64-bit branch likes to crash and is generally unstable. Needed patches to update webview for that to even work.

### [Just Cause 3](https://store.steampowered.com/app/225540/Just_Cause_3/)
- Works pretty much flawlessly. Clicking off the window may disable Fullscreen Mode, you will have to turn it back on in the settings.
- To skip the intro videos:
  - [How-to](https://steamcommunity.com/sharedfiles/filedetails/?id=570542665). This uses the `dropzone` folder to replace the intro video with an empty file.
  - Launch options: `gamemoderun %command% --vfs-fs dropzone --vfs-archive patch_win64 --vfs-archive archives_win64 --vfs-archive dlc_win64 --vfs-fs`

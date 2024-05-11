---
title: Dauntless on Arch Linux
date: 2024-05-10 23:00:00 -000
categories: [gaming, linux]
tags: [linux, arch linux, gaming, dauntless, heroic]
---
![Dauntless Splash Art](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fassets.nintendo.com%2Fimage%2Fupload%2Fc_fill%2Cw_1200%2Fq_auto%3Abest%2Ff_auto%2Fdpr_2.0%2Fncom%2Fsoftware%2Fswitch%2F70010000020488%2F7a15fee1d27131140fd7e09512ace8269add3e64d2f88498aa5b5e602a2146e9&f=1&nofb=1&ipt=a4f9f566ccbd952932e8f20d5d4ffeeff27f2570d54ed2e9ba998ef6f69a3312&ipo=images)
## Introduction
Some friends invited me to get back into the game and seeing that EasyAntiCheat was being used, I knew it could probably work. Relevant information is:
- Kernel: 6.8.9-arch1-1
- Desktop Enviroment/Window Manager: Hyprland - Wayland compositor
- GPU: Nvidia
- Driver Version: 550.78 Stable Drivers
- Display: 3840x2160@144hz
- Launcher: Heroic

# Instructions
1) Download Heroic Game Launcher
```zsh
sudo pacman -Syu heroic-games-launcher-bin
```
2) Connect Epic Games Account through Heroic and download Dauntless. Be sure to select Proton 8.0 for your preferred version of Wine
3) After finishing the installation, go into the Dauntless(Settings) menu in Heroic and enable/set the following
a) Under the WINE menu: Enable Esync, Enable Fsync, Auto Install/Update DXVK-NVAPI on  Prefix
b) Under the OTHER menu: Enable 'Use GameMode' -> (download gamemode through pacman if you don't have it already), EasyAntiCheat Runtime
c) Under the ADVANCED menu: Under enviroment variables: 
  - Name=PROTON_EAC_RUNTIME
  - Value="/home/$USERNAME/.local/share/Steam/steamapps/common/Proton EasyAntiCheat Runtime"
  And another value:
  - Name=DXVK_ASYNC
  - Value=1
4) You will need to make a sym link(soft link) from the 'EasyAntiCheat' folder inside the 'Win64' folder.
Figure out where you installed Dauntless and go into that folder in a gui file manager(if you use a TUI file manager, you don't need this guide) where you should see the following files:
- 'Archon'
- 'EasyAntiCheat'
- 'Engine'
Right click the 'EasyAntiCheat' folder and select 'copy location'(using dolphin personally). Next you want to go into this path of folders:
- Archon/Binaries/Win64/
Then right click and select 'create new' -> 'link to file or directory'. Paste the path of the folder location you copied and make sure the name is set to 'EasyAntiCheat'.

# Conclusion
After doing the previous steps, you should be done and the game should launch with the "EasyAntiCheat Catalogue Not Found" error.
While I still do expirence a crash every few minutes, I'm working on improving the stability. These are good steps to get you started however.
If you ever need any technical help related to Dauntless however, join the ![discord link](http://discord.gg/dauntless Discord) and ask the user 'kurtfrag' in the technical-workarounds chat.

# Console-Specific 
## PlayStation
### Ripping a game CD on Linux
Using any CD, DVD or Bly Ray drive, insert the game CD into the drive. Make sure the device is unmounted. You can unmount it using the following command:

    udisksctl unmount -b /dev/sr0

Then, type the following two commands

    cdrdao read-cd --read-raw --datafile <game-name>.bin --device /dev/sr0 --driver generic-mmc-raw <game-name>.toc
    toc2cue <game-name>.toc <game-name>.cue
    
You will end up with the necessary `.bin` and `.cue` files.

## PlayStation 2
### Ripping a game DVD on Linux
Using any DVD or Blu Ray drive, insert the game DVD into the drive and type

    ddrescue /dev/sr0 <game-name>.iso

# Emulator Settings
## PlayStation
## Beetle-HW
1. Settings -> Drivers -> Video: vulkan (gl glitches for MGS)

## PlayStation 2
## PCSX2
1. Config -> Video -> Plugin Settings
    * Renderer: OpenGL (Hardware) (Jak & Daxter shadow glitches with Direct3D 11)
    * Internal Resolution (4x Native for 1080p screens, 5x Native for 4K screens)
    * Advanced Settings and Hacks -> [x] Align Sprite (Tekken Tag Tournament lines across screen glitches without it)
    * Advanced Settings and Hacks -> SkipDraw Range: 0 (Okami strange textures for brushes)
    * Emulation Settings -> Speedhacks -> [x] MTVU (Performance Boost, no observed glitches)

# libretro-xemu-launcher


![social_banner](https://github.com/new-penguin/libretro-xemu-launcher-antimicrox/assets/139792946/a0e4520f-0b88-4811-8961-d4d82fd34727)


Based on [libretro-dolphin-launcher](https://github.com/RobLoach/libretro-dolphin-launcher) and [libretro-PCSX2-launcher](https://github.com/eduardomozart/libretro-pcsx2-launcher). 

Launch Microsoft Xbox games through [Xemu](https://xemu.app/) directly from [RetroArch](http://www.libretro.com/) with full controller support using [antimicrox](https://github.com/AntiMicroX/antimicrox/).


## Installation

Download the Linux core from releases and skip to step 2 or...

1. Compile the core
  ``` bash
  git clone https://github.com/new-penguin/libretro-xemu-launcher-antimicrox
  cd libretro-xemu-launcher-antimicrox
  make
  ```

2. Copy the core file to the RetroArch cores directory. For example, to copy to the default core directory
  ``` bash
  cp xemu_launcher_libretro.so /usr/lib/libretro/xemu_launcher_libretro.so
  cp xemu_launcher_libretro.info /usr/share/libretro/info/xemu_launcher_libretro.info
  ```

3. Make sure [Xemu](https://xemu.app/) in installed as well as [antimicrox](https://github.com/AntiMicroX/antimicrox/) via your distro's repo or in my case, AUR repo. If not, you have the option to use the flatpak or appimage versions. You should be able to run both of the following commands:

  ``` bash
  xemu
  antimicrox
  ```
  or via flatpak
  
  ```
  flatpak run app.xemu.xemu
  flatpak run io.github.antimicrox.antimicrox
  ```
You can also use the appimage versions of the respective programs. Just copy both to your ~/.config/retroarch/system folder and make sure they're named xemu.AppImage and antimicrox.AppImage. Also don't forget to make them executable.

## Usage

1. Scan Microsoft Xbox games in RetroArch

2. Associate your games with the Microsoft Xbox (Xemu Launcher) core

3. Configure antimicrox to use your distro's 'close window' binding to your controller button preference. Or you can use my pre-configured controller mappings [here](https://ufile.io/9t4vnq6m) for the 360 and Xbox One controllers. Place in your user ~/ directory. In the provided examples I've mapped LS click + RS click to exit xemu. Also you should make sure xemu is configured correctly to run a game first as there's a bit of initial setup involved as well as controller configuration. Xemu's default config directory is ./local/share/xemu. You should have the files Complex_4627v1.03.bin, eeprom.bin, mcpx_1.0.bi and xbox_hdd.qcow2 (or other such hdd image) which can be found with an internet search. Once copied, configure Xemu to use them.
  
3. And once done you should be able to launch and switch games directly from the RetroArch menu

3. Alternatively, you can run games through the command line
  ``` bash
  retroarch -L xemu_launcher_libretro.so "game.iso"
  ```

## Contributors

- [Rob Loach](http://github.com/robloach)
- [Alcaro](https://github.com/Alcaro)
- [Eduardo Mozart de Oliveira](https://github.com/coldscientist)

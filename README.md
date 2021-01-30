# game-devices-udev
This repo contains udev rules to make supported controllers available with user-grade permissions

## How to set it up?
Thats easy!

### Archlinux
There is an [AUR package](https://aur.archlinux.org/packages/game-devices-udev/)←

### Others:
1. Download the [archive](https://gitlab.com/fabis_cafe/game-devices-udev/-/archive/main/game-devices-udev-main.zip)
2. extract
3. copy all the rule files to `/etc/udev/rules.d`
4. create another file: `/etc/modules-load.d/uinput.conf`
5. put `uinput` into that file
6. reboot

If everything was right, it should work now!

## Add my device!
### We need you help!
In order to create an udev rule, we need some infos
* Excact name (from the box, for example. Best case with a model-number)
* Output of `udevadm monitor --property` (You need to disconnect the device before running the command)
* Output of the device directly, like in `devadm info --query=all --attribute-walk --name=/dev/input/js0` or `udevadm info --query=all --attribute-walk --name=/dev/input/js1`

### Merge Request
In case you have a working rule and want to get it merged you're free to do this. Please do one MR for every device you want to add. Also do not forget to update the README.md with the device name. Format:
```
# [VENDOR] [MARKETING-DEVICE-NAME]; {CONNECTION-TYPE}; {CONNECTION-TYPE}
```

## Supported Devices
### 8Bitdo
* 8Bitdo F30 P1
* 8Bitdo F30 P2
* 8Bitdo N30
* 8Bitdo SF30
* 8Bitdo SN30
* 8Bitdo F30 Pro
* 8Bitdo N30 Pro
* 8Bitdo SF30 Pro
* 8Bitdo SN30 Pro
* 8Bitdo F30 Arcade
* 8Bitdo N30 Arcade
* 8Bitdo ZERO
* 8Bitdo Retro-Bit xRB8-64

### Alpha Imaging Technology Corp.
* VR Set

### Armor
* Armor PS4 Armor 3 Pad

### ASTRO Gaming
* ASTRO Gaming C40 Controller; USB

### Betop
* Betop PS4 Fun Controller

### EMiO
* EMiO PS4 Elite Controller

### Hori
* Hori RAP4
* Hori HORIPAD 4 FPS
* Hori HORIPAD 4 FPS Plus
* Hori HORIPAD S; USB
* Hori Nintendo Switch HORIPAD Wired Controller; USB

### HTC
* Various(?)

### Logitech

* Logitech F310 Gamepad; USB
* Logitech F710 Wireless Gamepad; USB #EXPERIMENTAL

### Mad Catz
* Mad Catz Street Fighter V Arcade FightPad PRO
* Mad Catz Street Fighter V Arcade FightStick TE S+

### Nacon
* Nacon PS4 Revolution Pro Controller

### Nintendo
* Nintendo Switch Pro Controller; bluetooth; USB
* Nintendo GameCube Controller / Adapter; USB

### NVIDIA
* NVIDIA Shield Portable (2013 - NVIDIA_Controller_v01.01 - In-Home Streaming only)
* NVIDIA Shield Controller (2017 - NVIDIA_Controller_v01.04); bluetooth
* NVIDIA Shield Controller (2015 - NVIDIA_Controller_v01.03); USB

### PDP
* PDP Afterglow Deluxe+ Wired Controller; USB
* PDP Nintendo Switch Faceoff Wired Pro Controller; USB

### PowerA
* PowerA Wired Controller for Nintendo Switch; USB
* PowerA Wireless Controller for Nintendo Switch; bluetooth

### Razer
* Razer Raiju PS4 Controller
* Razer Panthera Arcade Stick

### Sony
* Sony PlayStation DualShock 3; bluetooth; USB
* Sony PlayStation DualShock 4; bluetooth; USB
* Sony PlayStation DualShock 4 Slim; bluetooth; USB
* Sony PlayStation DualShock 4 Wireless Adapter; USB
* Sony DualSense Wireless-Controller; bluetooth; USB
* PlayStation VR

### Strikepad
* Strikepad PS4 Grip Add-on

### Valve
* Valve USB devices
* Valve Steam Controller
* Valve HID devices; bluetooth; USB
* Various-VR

### Zeroplus Technology Corporation
* Zeroplus Technology Corporation P4 (hitbox) #disabled for now

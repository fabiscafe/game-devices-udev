# game-devices-udev
This repo contains udev rules to make supported controllers available with user-grade permissions

## How to set it up?
Thats easy!

### Archlinux
There is an [AUR package](https://aur.archlinux.org/packages/game-devices-udev/)←

### Others:
1. Download the [archive](https://codeberg.org/fabiscafe/game-devices-udev/archive/main.zip)
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
# [VENDOR] [MARKETING-DEVICE-NAME]; {CONNECTION-TYPE}; {CONNECTION-TYPE} (VendorID:ProductID)
```
## Supported Devices
### 8Bitdo (2dc8)
* 8Bitdo F30 P1
* 8Bitdo F30 P2
* 8Bitdo N30
* 8Bitdo SF30
* 8Bitdo SN30
* 8Bitdo F30 Pro
* 8Bitdo N30 Pro
* 8Bitdo SF30 Pro
* 8Bitdo SN30 Pro
* 8BitDo SN30 Pro+; Bluetooth; USB
* 8Bitdo F30 Arcade
* 8Bitdo N30 Arcade
* 8Bitdo ZERO
* 8Bitdo Retro-Bit xRB8-64
* 8BitDo Pro 2; Bluetooth; USB (2dc8:6003)
* 8BitDo Pro 2 Wired; USB (2dc8:3106), (2dc8:3010) ([Setup Instructions](8BitDo.md))

### Alpha Imaging Technology Corp. (114d)
* VR Set (114d:8a12)

### ASTRO Gaming (9886)
* ASTRO Gaming C40 Controller; USB (9886:0025)

### Betop (11c0)
* Betop PS4 Fun Controller (11c0:4001)

### Hori (0f0d)
* Hori RAP4 (0f0d:008a)
* Hori HORIPAD 4 FPS (0f0d:0055)
* Hori HORIPAD 4 FPS Plus (0f0d:0066)
* Hori HORIPAD S; USB (0f0d:00c1)
* Hori Nintendo Switch HORIPAD Wired Controller; USB (0f0d:00c1)
* Hori Pokkén Tournament DX Pro Pad for Nintendo Switch; USB (0f0d:0092)

### HTC (0bb4)
* Unknown (0bb4:2c87)
* Unknown (0bb4:0306)
* Unknown (0bb4:0309)
* Unknown (0bb4:030a)
* Unknown (0bb4:030b)
* Unknown (0bb4:030c)
* Unknown (0bb4:030e)
* HTC VIVE Cosmos; USB (0bb4:030e)(057e:0315)(057e:0323)

### Logitech (046d)
* Logitech F310 Gamepad; USB (046d:c216)
* Logitech F710 Wireless Gamepad; USB (046d:c21f) #EXPERIMENTAL

### Mad Catz (0738)
* Mad Catz Street Fighter V Arcade FightPad PRO (0738:8250)
* Mad Catz Street Fighter V Arcade FightStick TE S+ (0738:8384)

### Microsoft (045e)
Microsoft Xbox360 Controller; USB (045e:028e) #EXPERIMENTAL
Microsoft Xbox 360 Wireless Receiver for Windows; USB (045e:0719)
Microsoft Xbox One S Controller; bluetooth; USB (045e:02ea) #EXPERIMENTAL

### Nacon (146b)
* Nacon PS4 Revolution Pro Controller (146b:0d01)

### Nintendo (057e)
* Nintendo Switch Pro Controller; bluetooth; USB (057e:2009)
* Nintendo GameCube Controller / Adapter; USB (057e:0337)
* Nintendo Switch Joy-Con (L); bluetooth (057e:2006)
* Nintendo Switch Joy-Con (R); bluetooth (057e:2007)

### NVIDIA (0955)
* NVIDIA Shield Portable (2013 - NVIDIA_Controller_v01.01 - In-Home Streaming only) (0955:7203)
* NVIDIA Shield Controller (2017 - NVIDIA_Controller_v01.04); bluetooth (0955:7214)
* NVIDIA Shield Controller (2015 - NVIDIA_Controller_v01.03); USB (0955:7210)

### PDP (0e6f)
* PDP Afterglow Deluxe+ Wired Controller; USB (0e6f:0188)
* PDP Nintendo Switch Faceoff Wired Pro Controller; USB (0e6f:0180)
* PDP Wired Fight Pad Pro for Nintendo Switch; USB (0e6f:0185)

### Personal Communication Systems, Inc. (0810)
* Personal Communication Systems, Inc. Twin USB Gamepad; USB (0810:e301)

### PowerA (20d6)
* PowerA Wired Controller for Nintendo Switch; USB (20d6:a711)
* PowerA Wireless Controller for Nintendo Switch; bluetooth (NA:NA)
* PowerA Zelda Wired Controller for Nintendo Switch; USB (20d6:a713)

### Razer (1532)
* Razer Raiju PS4 Controller (1532:1000)
* Razer Panthera Arcade Stick (1532:0401)
* Razer Raion PS4 Fightpad (1532:1100)

### Sony (054c)
* Sony PlayStation Strikepack; USB (054c:05c5)
* Sony PlayStation DualShock 3; bluetooth; USB + Motion Sensors (054c:0268)
* Sony PlayStation DualShock 4; bluetooth; USB (054c:05c4)
* Sony PlayStation DualShock 4 Slim; bluetooth; USB (054c:09cc)
* Sony PlayStation DualShock 4 Wireless Adapter; USB (054c:0ba0)
* Sony DualSense Wireless-Controller; bluetooth; USB (054c:0ce6)
* Sony DualSense Edge Wireless-Controller; bluetooth; USB (054c:0df2)
* PlayStation VR (054c:09af)

### Valve (28de)
* Valve USB devices (28de:*)
* Valve Steam Controller (28de:*)
* Valve HID devices; bluetooth; USB (28de:*)
* Unknown-VR (28de:1043)
* Unknown-VR (28de:1142)
* Unknown-VR (28de:2000)
* Unknown-VR (28de:2010)
* Unknown-VR (28de:2011)
* Unknown-VR (28de:2012)
* Unknown-VR (28de:2021)
* Unknown-VR (28de:2022)
* Unknown-VR (28de:2050)
* Unknown-VR (28de:2101)
* Unknown-VR (28de:2102)
* Unknown-VR (28de:2150)
* Unknown-VR (28de:2300)
* Unknown-VR (28de:2301)

### Zeroplus Technology Corporation (0c12)
* Armor PS4 Armor 3 Pad; USB (0c12:0e10)
* EMiO PS4 Elite Controller; USB (0c12:1cf6)
* Hit Box Arcade HIT BOX PS4/PC version; USB (0c12:0ef6)
* Nyko Xbox Controller; USB (0c12:8801)
* Unknown-Brand Xbox Controller; USB (0c12:8802)
* Unknown-Brand Xbox Controller; USB (0c12:8810)

## Known Issues
### 8Bitdo SN30 Pro+
In Android mode (START+B), if connected via cable the controller starts up, but gets removed by the kernel in most cases again. This does not happen all the time and there is nothing udev can do about.

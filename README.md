# game-devices-udev
This repo contains udev rules to make supported controllers available with user-grade permissions.

## How to set it up?

### Arch Linux
There is an [AUR package](https://aur.archlinux.org/packages/game-devices-udev/).

### NixOS
Install the rules under `services.udev.packages` in the `configuration.nix` file.
1. Add the following to your `configuration.nix`:
   ```nix
   services = {
     udev = {
       packages = with pkgs; [
         game-devices-udev-rules
       ];
     };
   };
   ```
2. (Optional) Add the following to your `configuration.nix`:
   ```nix
   hardware.uinput.enable = true;
   ```
3. Rebuild the system with `nixos-rebuild`.

### Others:
1. Download the [archive](https://codeberg.org/fabiscafe/game-devices-udev/archive/main.zip).
2. Extract the archive.
3. Copy all the rule files to `/etc/udev/rules.d`.
4. Create another file: `/etc/modules-load.d/uinput.conf`.
5. Put `uinput` into that file.
6. Reboot.

If everything was done correctly, it should work now!

## Add My Device!
### Create a Pull/Merge Request!
Please create a pull request with your verified working rule, one rule per device. Also, do not forget to include the README.md change, with the device name format:
```
# [VENDOR] [MARKETING-DEVICE-NAME]; {CONNECTION-TYPE}; {CONNECTION-TYPE} (VendorID:ProductID)
```
### Need Help Writing a Rule?
If you're having trouble, consider reaching out to a Linux community for assistance. Here are some helpful steps to gather information:

1. **Device Information**: Provide the exact (marketing) name and model number of your device; this is also needed for the README.md.
2. **Monitor Device Events**: Run the following command before connecting or disconnecting your device to capture its information:
   ```bash
   udevadm monitor --property
   ```
3. **Device Details**: Use the following command to get detailed information about your device:
   ```bash
   udevadm info --query=all --attribute-walk --name=/dev/input/js0
   # /dev/input/js0 is the path of your device; it could also be /dev/input/js1 or something else.
   ```

## Supported Devices

### 8BitDo (2dc8)
* 8BitDo Generic Device; (2dc8:3106)
* 8BitDo F30 P1
* 8BitDo F30 P2
* 8BitDo N30
* 8BitDo SF30
* 8BitDo SN30
* 8BitDo F30 Pro
* 8BitDo N30 Pro
* 8BitDo SF30 Pro
* 8BitDo SN30 Pro
* 8BitDo SN30 Pro+; Bluetooth; USB
* 8BitDo F30 Arcade
* 8BitDo N30 Arcade
* 8BitDo ZERO
* 8BitDo Retro-Bit xRB8-64
* 8BitDo Pro 2; Bluetooth; USB (2dc8:6003)
* 8BitDo Pro 2 Wired; USB (2dc8:3010) ([Setup Instructions](8BitDo.md))
* 8BitDo Ultimate Wired Controller for Xbox; USB (2dc8:2003)
* 8BitDo Ultimate 2.4G Wireless Controller; USB/2.4GHz (2dc8:3012)
* 8BitDo Ultimate 2C Wireless Controller; USB/2.4GHz (2dc8:310a)
* 8BitDo Arcade Stick; Bluetooth (X-mode)
* 8BitDo Ultimate 2 Wireless Controller; Bluetooth; USB/2.4GHz (2dc8:310b)

### Alpha Imaging Technology Corp. (114d)
* VR Set (114d:8a12)

### ASTRO Gaming (9886)
* ASTRO Gaming C40 Controller; USB (9886:0025)

### Betop (11c0)
* Betop PS4 Fun Controller (11c0:4001)

### Cypress Semiconductor Corp. [+Flydigi] (04b4)
* Flydigi Apex 4 Controller; Bluetooth; USB (04b4:2412)

### Google (18d1)
* Google Stadia Controller; Bluetooth; USB (18d1:9400)

### Hori (0f0d)
* Hori RAP4 (0f0d:008a)
* Hori HORIPAD 4 FPS (0f0d:0055)
* Hori HORIPAD 4 FPS Plus (0f0d:0066)
* Hori HORIPAD S; USB (0f0d:00c1)
* Hori Nintendo Switch HORIPAD Wired Controller; USB (0f0d:00c1)
* Hori Pokkén Tournament DX Pro Pad for Nintendo Switch; USB (0f0d:0092)
* Hori Wireless HORIPAD for Steam; USB (0f0d:01ab)

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
* Microsoft Xbox 360 Controller; USB (045e:028e) #EXPERIMENTAL
* Microsoft Xbox 360 Wireless Receiver for Windows; USB (045e:0719)
* Microsoft Xbox One S Controller; Bluetooth; USB (045e:02ea) #EXPERIMENTAL
* Microsoft Xbox One Controller; Bluetooth; USB (045e:02fd)

### Nacon (146b)
* Nacon PS4 Revolution Pro Controller (146b:0d01)

### Nintendo (057e)
* Nintendo Switch Pro Controller; Bluetooth; USB (057e:2009)
* Nintendo GameCube Controller / Adapter; USB (057e:0337)
* Nintendo Switch Joy-Con Charging Grip (057e:200e)
* Nintendo Switch Joy-Con (L); Bluetooth (057e:2006)
* Nintendo Switch Joy-Con (R); Bluetooth (057e:2007)

### NVIDIA (0955)
* NVIDIA Shield Portable (2013 - NVIDIA_Controller_v01.01 - In-Home Streaming only) (0955:7203)
* NVIDIA Shield Controller (2017 - NVIDIA_Controller_v01.04); Bluetooth (0955:7214)
* NVIDIA Shield Controller (2015 - NVIDIA_Controller_v01.03); USB (0955:7210)

### Performance Designed Products LLC [PDP] (0e6f)
* PDP Afterglow Deluxe+ Wired Controller; USB (0e6f:0188)
* PDP Nintendo Switch Faceoff Wired Pro Controller; USB (0e6f:0180)
* PDP Wired Fight Pad Pro for Nintendo Switch; USB (0e6f:0185)

### Personal Communication Systems, Inc. (0810)
* Personal Communication Systems, Inc. Twin USB Gamepad; USB (0810:e301)

### Pid.Codes (1209)
* EdgeTX, OpenTX Generic [radio controller] Joystick; USB (1209:4f54)

### PowerA (20d6)
* PowerA Wired Controller for Nintendo Switch; USB (20d6:a711)
* PowerA Wireless Controller for Nintendo Switch; Bluetooth (NA:NA)
* PowerA Zelda Wired Controller for Nintendo Switch; USB (20d6:a713)

### Razer (1532)
* Razer Raiju PS4 Controller (1532:1000)
* Razer Panthera Arcade Stick (1532:0401)
* Razer Raion PS4 Fightpad (1532:1100)

### Sony (054c)
* Sony PlayStation Strikepack; USB (054c:05c5)
* Sony PlayStation DualShock 3; Bluetooth; USB + Motion Sensors (054c:0268)
* Sony PlayStation DualShock 4; Bluetooth; USB (054c:05c4)
* Sony PlayStation DualShock 4 Slim; Bluetooth; USB (054c:09cc)
* Sony PlayStation DualShock 4 Wireless Adapter; USB (054c:0ba0)
* Sony DualSense Wireless-Controller; Bluetooth; USB (054c:0ce6)
* Sony DualSense Edge Wireless-Controller; Bluetooth; USB (054c:0df2)
* PlayStation VR (054c:09af)

### Valve (28de)
* Valve USB devices (28de:*)
* Valve Steam Controller (28de:*)
* Valve HID devices; Bluetooth; USB (28de:*)
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
### 8BitDo SN30 Pro+
In Android mode (START+B), if connected via cable the controller starts up, but gets removed by the kernel in most cases again. This does not happen all the time and there is nothing udev can do about.

## Related Projects
* [udev-joystick-blacklist](https://github.com/denilsonsa/udev-joystick-blacklist) - Fix for keyboard/mouse/tablet being detected as joystick in Linux.
* [steam-devices](https://github.com/ValveSoftware/steam-devices) - List of devices Steam and SteamVR will want read/write permissions on.

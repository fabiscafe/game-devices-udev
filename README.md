# Steam-devices
This repo contains udev rules to make some controllers available for the users system

## How to set it up?
Thats easy!

1. Download the [archive](https://gitlab.com/Fabish/steam-devices/-/archive/master/steam-devices-master.zip)
2. Extrackt
3. copy all the rule files to `/etc/udev/rules.d`
4. create another file: `/etc/modules-load.d/uinput.conf`
5. put `uinput` into that file
6. reboot

If everything was right, it should work now!

## How to set it up on Manjaro?
`pacman -Syu steam-devices` 

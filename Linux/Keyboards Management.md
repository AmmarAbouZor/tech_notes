### Remap Keys with udev

This enables remapping keys at the `udev` level, making the changes independent of the desktop environment.

First, we need the `evtest` tool to get the keyboard name and the key code.

Run `evtest` with `sudo` to list connected input devices and select your keyboard. Press the desired key to identify its key code, and note the keyboard's exact name as listed by `evtest`.

After getting this information, create a `.hwdb` file in `/etc/udev/hwdb.d/`. Inside the file, define the mapping rule using the keyboard name and key code. Finally, update `udev` with the following commands:

```sh
sudo systemd-hwdb update
sudo udevadm trigger
```

#### Example: Right alt to shift:

This example shows how to bind right alt to right shift on multiple files:
* Create the file `/etc/udev/hwdb.d/right-alt-right-shift.hwdb` with the following content:

```
####################################
### Map right alt to right shift ###
####################################

# Built in device:
evdev:atkbd:*
 KEYBOARD_KEY_b8=rightshift

# Ohter keyboards:
evdev:name:Logitech ERGO K860:*
evdev:name:Logitech USB Keyboard:*
 KEYBOARD_KEY_700e6=rightshift
```

#### Example: <> to shift in ISO layout

This example remaps the key next to the left Shift key on an ISO layout keyboard to function as Left Shift, specifically for the `Logitech ERGO K860`.

* Create the file `/etc/udev/hwdb.d/iso-shift.hwdb` with the following content:

```
#############################
### Map `<>` key to shift ###
#############################

evdev:name:Logitech ERGO K860:*
 KEYBOARD_KEY_70064=leftshift
```

* Keyboard name used: `Logitech ERGO K860`
* Keycode for `<>` key identified: `70064`

#### Links:

* [Example](https://unix.stackexchange.com/questions/750311/how-to-remap-a-regular-key-into-a-modifier-key-shift-in-linux)
* [Arch WIKI](https://wiki.archlinux.org/title/Map_scancodes_to_keycodes)


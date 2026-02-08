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


----

### ANSI US Layout with German Support

Gnome has an ANSI US layout with best support for German chars. This layout isn't visible by default and can be enabled from the command line via:

```sh
gsettings set org.gnome.desktop.input-sources show-all-sources true
```

After enabling it we can find the layout as one of the options under **English (United States)** with the name **German, Swedish and Finish (US)**.
Then we can modify the *alternate chars key* to something like right control. 
=======

### Apple magic keyboard

In the file `/etc/modprobe.d/hid-apple.conf` enter the following:

```
# Make tilde/grave key work correctly
# Make F-keys act as F-keys by default
# Swap Option (Alt) and Command (Super) keys

options hid_apple iso_layout=0 fnmode=2 swap_opt_cmd=1
```
Then the command

```sh
sudo update-initramfs -u
```
Then reboot.

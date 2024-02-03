## Reset fonts from the command line

```bash
gsettings reset org.gnome.desktop.wm.preferences titlebar-font
gsettings reset org.gnome.desktop.interface monospace-font-name
gsettings reset org.gnome.desktop.interface document-font-name
gsettings reset org.gnome.desktop.interface font-name
```

## Keybindings

### Get all keybindings
To get all the keybindings from gnome you can use:
```bash
(for schema in $(gsettings list-schemas); do gsettings list-recursively $schema; done) | grep '<Super>'
```

### Free Super+O 
```bash
gsettings set org.gnome.settings-daemon.plugins.media-keys rotate-video-lock-static []
```

### Free Super+P 
Super P control the monitors in gnome. It could be remapped like this
```bash
gsettings set org.gnome.mutter.keybindings switch-monitor "['<Super>slash', 'XF86Display']"
```

### Turn screens off
This bind can be done on the settings GUI
```bash
xdg-screensaver activate
```

## Launch app using discrete GPU
Gnome uses the package `switechroo-controls`. 

```bash
switcherooctl launch <command>

switcherooctl launch kitty
```
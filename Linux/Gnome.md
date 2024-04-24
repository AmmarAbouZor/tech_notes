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

## Log in from external Monitor

You need to your current monitor settings to gdm configuration folder.
After setting the monitor configs via gnome settings app use the following command:
```bash
sudo cp ~/.config/monitors.xml /val/lib/gdm/.config/
```

## Running script on start

To run scripts after the start of gnome desktop you need to create a `*.desktop` file in `~/.config/autostart`
Here is an example:
```bash
[Desktop Entry]
Name=MyScript
GenericName=A descriptive name
Comment=Some description about your script
Exec=/path/to/my/script.sh # Or the script itself
Terminal=false
Type=Application
X-GNOME-Autostart-enabled=true
```

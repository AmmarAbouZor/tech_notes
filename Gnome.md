## Reset fonts from the command line

```bash
gsettings reset org.gnome.desktop.wm.preferences titlebar-font
gsettings reset org.gnome.desktop.interface monospace-font-name
gsettings reset org.gnome.desktop.interface document-font-name
gsettings reset org.gnome.desktop.interface font-name
```

## Free Super+O command

```bash
gsettings set org.gnome.settings-daemon.plugins.media-keys rotate-video-lock-static []
```

To get all the keybindings from gnome you can use:
```bash
(for schema in $(gsettings list-schemas); do gsettings list-recursively $schema; done) | grep '<Super>'
```

## German Characters Table

| Letter | Code|
|-------|------|
|ß|00df|
|ä|00e4|
|ö|00f6|
|ü|00fc|
|Ä|00c4|
|Ö|00d6|
|Ü|00dc|

## Send German Ibus on Linux 
In Gnome there is support for Ibus application which allow to send the unicode of a character and it will insert it.
The shortcut for that is Ctrl+Shift+U => type unicode => Space or Ctrl
For example `Ctrl+Shift+U 00fc <space>` prints `ü`
Here 
This can be used with macros with ZMK or QMK firmware
With QMK this can be done easily with VIA
Here is an example for ZMK [[ZMK#Macro to Send Unicodes with Ibus]]

## Windows

In windows there is another way to send the unicode characters using holding `alt` . To find all the information search for `insert unicode characters in widnows`
Here is an example for ZMK [[ZMK#Macro to Send Unicode in Windows]]

## Macro to Send Unicodes with Ibus
Here is an example of sending an unicode with Ibus thats works on Linux 
```dts
macros {
	ibus_de_a: ibus_de_a {
        label = "IBUS_GERMAN_A";
        compatible = "zmk,behavior-macro";
        #binding-cells = <0>;
        tap-ms = <0>;
        wait-ms = <0>;
        bindings
            = <&macro_press &kp LCTRL &kp LSHFT>
            , <&macro_tap &kp U>
            , <&macro_release &kp LCTRL &kp LSHFT>
            , <&macro_tap &kp N0 &kp N0 &kp E &kp N4 &kp SPC>
            ;
    }; 
};
```

## Macro to Send Unicode in Windows
In windows we send the Unicode while holding ALT
```dts
macros {
    // Windows German Characters Unicode
    win_de_a: win_de_a {
        label = "WIN_GERMAN_A";
        compatible = "zmk,behavior-macro";
        #binding-cells = <0>;
        tap-ms = <0>;
        wait-ms = <0>;
        bindings
            = <&macro_press &kp RALT>
            , <&macro_tap &kp KP_N1 &kp KP_N3 &kp KP_N2>
            , <&macro_release &kp RALT>
            ;
    }; 
};
```

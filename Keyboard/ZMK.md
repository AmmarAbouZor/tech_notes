
## Macro to Send Unicodes with Ibus
Here is an example of sending an unicode with Ibus thats works on Linux 
```dts
macros {
    uc_dash: uc_dash {
        label = "UNICODE_DASH";
        compatible = "zmk,behavior-macro";
        #binding-cells = <0>;
        tap-ms = <0>;
        wait-ms = <0>;
        bindings
            = <&macro_press &kp LCTRL &kp LSHFT>
            , <&macro_tap &kp U>
            , <&macro_release &kp LCTRL &kp LSHFT>
            , <&macro_tap &kp N2 &kp N0 &kp N1 &kp N4 &kp SPC>
            ;
    }; 
};
```

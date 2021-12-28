
# Boot

## Subject

* [Xsession](#xsession)
* [Autostart](#autostart)
* [Howto](#howto)


## Xsession

| Path | Note |
| --- | --- |
| [/usr/share/xsessions/hyprwm-session.desktop](xsessions/hyprwm-session.desktop) | start here |
| [/usr/share/hyprwm/xsessions/hyprwm-session](xsessions/hyprwm-session) | hyprwm-session.desktop call this script |


## Autostart

> Not using system wild if user file exists.

### System Wild

| Path |
| --- |
| [/usr/share/hyprwm/config/hyprwm/environment](config/hyprwm/environment) |
| [/usr/share/hyprwm/config/hyprwm/autostart](config/hyprwm/autostart) |


### Per User

| Path |
| --- |
| [~/.config/hypr/environment](../asset/config/environment) |
| [~/.config/hypr/autostart](../asset/config/autostart) |


## Howto

### Install

``` sh
make install
```

### Remove

``` sh
make remove
```

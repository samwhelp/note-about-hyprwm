
# User Config


## Subject

* [User Config Dir Path](#user-config-dir-path)
* [User Config File List](#user-config-file-list)
* [Howto](#howto)
* [Spec](#spec)
* [Link](#link)
* [Test Command](#test-command)


## User Config Dir Path

* [~/.config/hypr](./config/hypr)


## User Config File List

run

``` sh
tree --dirsfirst ~/.config/hypr
```

show

```
/home/user/.config/hypr
├── style
│   └── picom
│       └── picom.conf
├── autostart
├── environment
└── hypr.conf

2 directories, 4 files
```

## Howto

### Install

``` sh
make install
```

### Remove

``` sh
make remove
```


## Spec

* [Keybind](spec-keybind.md)


## Link

* Hypr / issues / [#28 Missing documentation?](https://github.com/vaxerski/Hypr/issues/28)


## Test Command

``` sh
xmodmap -pk
```

``` sh
xev -event keyboard
```

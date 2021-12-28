default: help
.PHONY: default

help:
	@echo 'Usage:'
	@echo '	$$ make [action]'
	@echo
	@echo 'Example:'
	@echo '	$$ make'
	@echo '	$$ make help'
	@echo
	@echo '	$$ make clone'
	@echo
	@echo '	$$ make prepare-arch-build'
	@echo
	@echo '	$$ make prepare-ubuntu-build'
	@echo
	@echo '	$$ make build'
	@echo
	@echo '	$$ make install'
	@echo
	@echo '	$$ make remove'
	@echo

.PHONY: help


install: hyprwm-install xsession-install config-install
.PHONY: install

remove: hyprwm-remove xsession-remove config-remove
.PHONY: remove


##
## * https://github.com/vaxerski/Hypr
## * https://github.com/vaxerski/Hypr/wiki
## * https://github.com/vaxerski/Hypr/wiki/Building
##

prepare-arch-build:
	sudo pacman -S --needed cairo gdb ninja gcc cmake libxcb xcb-proto xcb-util xcb-util-cursor xcb-util-keysyms xcb-util-wm gtkmm gtk4 gtkmm3
.PHONY: prepare-arch-build

prepare-ubuntu-build:
	sudo apt-get install xcb cmake gcc libgtk-3-dev ninja-build libgtkmm-3.0-dev libxcb-randr0 libxcb-randr0-dev libxcb-util-dev libxcb-util0-dev libxcb-util1 libxcb-ewmh-dev libxcb-xinerama0 libxcb-xinerama0-dev libxcb-icccm4-dev libxcb-keysyms1-dev libxcb-cursor-dev libxcb-shape0-dev build-essential
.PHONY: prepare-ubuntu-build

clone:
	git clone https://github.com/vaxerski/Hypr.git src/hyprwm
.PHONY: clone

build:
	make -C src/hyprwm clear
	make -C src/hyprwm release
.PHONY: build

#hyprwm-install: build
hyprwm-install:
	sudo install -Dm755 ./src/hyprwm/build/Hypr /usr/bin/Hypr
#	sudo install -Dm755 ./src/hyprwm/build/Hypr /usr/local/bin/Hypr
.PHONY: hyprwm-install


hyprwm-remove:
	sudo rm -f /usr/bin/Hypr
#	sudo rm -f /usr/local/bin/Hypr
.PHONY: hyprwm-remove




xsession-install:
	make -C ./asset/xsession install
.PHONY: xsession-install

xsession-remove:
	make -C ./asset/xsession remove
.PHONY: xsession-remove




config-install:
	make -C ./asset/config install
.PHONY: config-install

config-remove:
	make -C ./asset/config remove
.PHONY: config-remove

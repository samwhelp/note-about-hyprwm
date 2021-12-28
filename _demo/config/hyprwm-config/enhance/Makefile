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
	@echo '	$$ make prepare_arch_build'
	@echo
	@echo '	$$ make prepare_ubuntu_build'
	@echo
	@echo '	$$ make build'
	@echo
	@echo '	$$ make install'
	@echo
	@echo '	$$ make remove'
	@echo

.PHONY: help


install: hyprwm_install xsession_install config_install
.PHONY: install

remove: hyprwm_remove xsession_remove config_remove
.PHONY: remove


##
## * https://github.com/vaxerski/Hypr
## * https://github.com/vaxerski/Hypr/wiki
## * https://github.com/vaxerski/Hypr/wiki/Building
##

prepare_arch_build:
	sudo pacman -S --needed cairo gdb ninja gcc cmake libxcb xcb-proto xcb-util xcb-util-cursor xcb-util-keysyms xcb-util-wm gtkmm gtk4 gtkmm3
.PHONY: prepare_arch_build

prepare_ubuntu_build:
	sudo apt-get install xcb cmake gcc libgtk-3-dev ninja-build libgtkmm-3.0-dev libxcb-randr0 libxcb-randr0-dev libxcb-util-dev libxcb-util0-dev libxcb-util1 libxcb-ewmh-dev libxcb-xinerama0 libxcb-xinerama0-dev libxcb-icccm4-dev libxcb-keysyms1-dev libxcb-cursor-dev libxcb-shape0-dev build-essential
.PHONY: prepare_ubuntu_build

clone:
	git clone https://github.com/vaxerski/Hypr.git src/hyprwm
.PHONY: clone

build:
	make -C src/hyprwm clear
	make -C src/hyprwm release
.PHONY: build

#hyprwm_install: build
hyprwm_install:
	sudo install -Dm755 ./src/hyprwm/build/Hypr /usr/bin/Hypr
#	sudo install -Dm755 ./src/hyprwm/build/Hypr /usr/local/bin/Hypr
.PHONY: hyprwm_install


hyprwm_remove:
	sudo rm -f /usr/bin/Hypr
#	sudo rm -f /usr/local/bin/Hypr
.PHONY: hyprwm_remove




xsession_install:
	make -C ./asset/xsession install
.PHONY: xsession_install

xsession_remove:
	make -C ./asset/xsession remove
.PHONY: xsession_remove




config_install:
	make -C ./asset/config install
.PHONY: config_install

config_remove:
	make -C ./asset/config remove
.PHONY: config_remove

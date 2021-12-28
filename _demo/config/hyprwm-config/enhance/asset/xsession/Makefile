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
	@echo '	$$ make install'
	@echo
	@echo '	$$ make remove'
	@echo

.PHONY: help


install: xsession-install config-install
.PHONY: install

xsession-install:
	sudo install -Dm644 ./xsessions/hyprwm-session.desktop /usr/share/xsessions/hyprwm-session.desktop
	sudo install -Dm755 ./xsessions/hyprwm-session /usr/share/hyprwm/xsessions/hyprwm-session
.PHONY: xsession-install

config-install:
	sudo install -Dm644 ./config/hyprwm/environment /usr/share/hyprwm/config/hyprwm/environment
	sudo install -Dm755 ./config/hyprwm/autostart /usr/share/hyprwm/config/hyprwm/autostart
.PHONY: config-install




remove: xsession-remove config-remove
.PHONY: remove

xsession-remove:
	sudo rm -f /usr/share/xsessions/hyprwm-session.desktop
	sudo rm -f /usr/share/hyprwm/xsessions/hyprwm-session
.PHONY: xsession-remove

config-remove:
	sudo rm -f /usr/share/hyprwm/config/hyprwm/environment
	sudo rm -f /usr/share/hyprwm/config/hyprwm/autostart
.PHONY: config-remove

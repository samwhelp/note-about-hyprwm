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
	@echo '	$$ make test'
	@echo

.PHONY: help


install: autostart-install config-install compositor-install wallpaper-install
#	tree --dirsfirst ~/.config/hypr
.PHONY: install

autostart-install:
	install -Dm644 ./hypr/environment ~/.config/hypr/environment
	install -Dm755 ./hypr/autostart ~/.config/hypr/autostart
.PHONY: autostart-install

config-install:
	install -Dm644 ./hypr/hypr.conf ~/.config/hypr/hypr.conf
.PHONY: config-install

compositor-install:
	install -Dm644 ./hypr/style/picom/picom.conf ~/.config/hypr/style/picom/picom.conf
.PHONY: compositor-install

wallpaper-install:
	install -Dm755 ./hypr/bin/hypr-wallpaper-ctrl-shuf ~/.config/hypr/bin/hypr-wallpaper-ctrl-shuf
	install -Dm755 ./hypr/bin/hypr-wallpaper-ctrl-default ~/.config/hypr/bin/hypr-wallpaper-ctrl-default
.PHONY: wallpaper-install


remove: autostart-remove config-remove compositor-remove wallpaper-remove
#	tree --dirsfirst ~/.config/hypr
.PHONY: remove

autostart-remove:
	rm -f ~/.config/hypr/environment
	rm -f ~/.config/hypr/autostart
.PHONY: autostart-remove

config-remove:
	rm -f ~/.config/hypr/hypr.conf
.PHONY: config-remove

compositor-remove:
	rm -f  ~/.config/hypr/style/picom/picom.conf
.PHONY: compositor-remove

wallpaper-remove:
	rm -f  ~/.config/hypr/bin/hypr-wallpaper-ctrl-shuf
	rm -f  ~/.config/hypr/bin/hypr-wallpaper-ctrl-default
.PHONY: wallpaper-remove



test:
	./xephyr-run-hypr.sh
.PHONY: test

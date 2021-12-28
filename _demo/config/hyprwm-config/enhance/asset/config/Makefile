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


install: autostart-install config-install picom-install
#	tree --dirsfirst ~/.config/hypr
.PHONY: install

autostart-install:
	install -Dm644 ./hypr/environment ~/.config/hypr/environment
	install -Dm755 ./hypr/autostart ~/.config/hypr/autostart
.PHONY: autostart-install

config-install:
	install -Dm644 ./hypr/hypr.conf ~/.config/hypr/hypr.conf
.PHONY: config-install

picom-install:
	install -Dm644 ./hypr/style/picom/picom.conf ~/.config/hypr/style/picom/picom.conf
.PHONY: picom-install




remove: autostart-remove config-remove picom-remove
#	tree --dirsfirst ~/.config/hypr
.PHONY: remove

autostart-remove:
	rm -f ~/.config/hypr/environment
	rm -f ~/.config/hypr/autostart
.PHONY: autostart-remove

config-remove:
	rm -f ~/.config/hypr/hypr.conf
.PHONY: config-remove

picom-remove:
	rm -f  ~/.config/hypr/style/picom/picom.conf
.PHONY: picom-remove



test:
	./xephyr-run-hypr.sh
.PHONY: test

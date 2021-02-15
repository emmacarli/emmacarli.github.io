---
layout: post
title:  "Check Point VPN installation"
date:   2020-02-12 10:00:00
blurb: "How to install Check Point Endpoint Security VPN on Ubuntu 20.04."
---


Ubuntu 20.04 64 bit

Download from: [https://starkers.keybase.pub/snx_install_linux30.sh?dl=1](https://starkers.keybase.pub/snx_install_linux30.sh?dl=1). This is an older version, newer versions don't seem to work.

Extract the files, then:

	sudo dpkg --add-architecture i386
	sudo apt-get update    

	sudo apt-get install libstdc++5:i386 libx11-6:i386 libpam0g:i386
	chmod a+rx snx_install_linux30.sh
	sudo ./snx_install_linux30.sh
	
Sources:
- [https://unix.stackexchange.com/questions/477689/linux-checkpoint-snx-tool-configuration-issues](https://unix.stackexchange.com/questions/477689/linux-checkpoint-snx-tool-configuration-issues)
- [https://unix.stackexchange.com/questions/450229/getting-checkpoint-vpn-ssl-network-extender-working-in-the-command-line](https://unix.stackexchange.com/questions/450229/getting-checkpoint-vpn-ssl-network-extender-working-in-the-command-line)

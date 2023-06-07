# Making A List of Assholes

### whois / nicsearch

	- Download Go

			https://go.dev/dl/

	- Install Go

			https://go.dev/doc/install

	- Install `nicsearch`

			go install github.com/BourgeoisBear/nicsearch@latest

### download & build cidrmerge

	https://cidrmerge.sourceforge.net/
	https://sourceforge.net/projects/cidrmerge/files/cidrmerge/cidrmerge-1.5.3/cidrmerge-1.5.3.tar.gz/download

### make assholes list

	nicsearch 'cc RU' | grep IPV4 | cut -d\| -f4 | cidrmerge

# Blocking Assholes on Linux

### disable iptables

	apt-get remove iptables

### install & enable nftables

	apt-get install nftables
	systemctl enable nftables.service

### nft base config

	/etc/nftables.conf
	/etc/assholes.list

### check nft ruleset

	nft -c -f /etc/nftables.conf

### deploy nft ruleset

	nft -f /etc/nftables.conf

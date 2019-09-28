
**XeroChainNode setup guide**

Download *Raspbian Buster Lite* [Link](https://www.raspberrypi.org/downloads/raspbian/)

Direct links:
[Torrent](https://downloads.raspberrypi.org/raspbian_lite_latest.torrent) - [Https](https://downloads.raspberrypi.org/raspbian_lite_latest)

Unzip the downloaded file, and burn the .img with f.ex _Win32 Disk Imager_ [Link](https://sourceforge.net/projects/win32diskimager/)

_For SSH access without monitor on first boot, include a file called "ssh" in root of the 'boot' partition on the sd-card. The file should contain ONLY `ECHO is on.` and have NO extention._

With a monitor attached, or with SSH, log with:

	User: pi
	Password: raspberry

Set root password

	sudo -i
	passwd
	

Add xero user

	sudo adduser xero
	sudo adduser xero sudo
	su - xero

Install 

	wget https://github.com/xero-official/scripts/releases/download/1.0.0/armchainnode.sh
	chmod +x armchainnode.sh
	./armchainnode.sh

On the dashboard:

	Add your node by entering "1"
	Select your type of node from the list (Chain Node) 
	Paste your private key containing the nodes collateral
**Congratulations your node setup is complete.**


To check status:

`systemctl status xerochainnode`

To see your Node ID again:

`/usr/sbin/geth --exec "admin.nodeInfo.enode" attach ipc://./$HOME/.xerom/geth.ipc`

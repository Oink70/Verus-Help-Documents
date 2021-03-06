__***Guide to install Bootstrap into Agama Wallet. Read it completely before using.***__

__*`Agama Wallet location` on different OS:*__
Linux GUI:	`~/.Komodo/VRSC`
Mac OS: 	`/Users/<YOURUSERNAME>/Library/Application Support/Komodo/VRSC`
Windows 10: 	`%AppData%\Roaming\Komodo\VRSC\`

__*Usefull auxilairy Windows software:*__
Checksum utility:	https://raylin.wordpress.com/downloads/md5-sha-1-checksum-utility/
7-zip:			https://www.7-zip.org/

__*Procedure:*__
1) Make sure Agama is not active.
2) If you had Agama running _before_, backup essential files:
	2a) Go to `Agama Wallet location`
	2b) copy `Wallet.dat` to a __*safe*__ location
	2c) copy `VRSC.conf` to a __*safe*__ location
	2d) Verify that both files are copied to your safe location
3) Make sure the _latest_ version of Agama Wallet for Verus is installed
	3a) Download the _latest_ Agama Verus Wallet from this location: https://veruscoin.io/
	3b) Verify the SHA256 checksum of your download, so you have an untampered installer.
	3c) Run the file you just downloaded to install it.
4) Download the bootstrap from https://bootstrap.0x03.services/veruscoin/VRSC.html and verify the checksum
5) Unpack (using 7-zip when in Windows) the downloaded archive to `Agama Wallet location`
6) If you had Agama running before, restore essential files:
	6a) Go to `Agama Wallet location`
	6b) Verify that your `Wallet.dat` is bigger than the one in this folder (if any is present)
	6c) copy `Wallet.dat` from your __*safe*__ location
	6c) copy `VRSC.conf` from your __*safe*__ location
7) Start Agama

If you followed these steps, you will have installed/updated the latest version of Agama for verus, made a backup of your wallet and installed the bootloader.

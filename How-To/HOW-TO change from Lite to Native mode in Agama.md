__***Guide to change Agama from Lite Mode to Native Mode.***__

__*`Agama Wallet location` on different OS:*__
Linux GUI:	`~/.Komodo/VRSC`
Mac OS: 	`/Users/<YOURUSERNAME>/Library/Application Support/Komodo/VRSC`
Windows 10: 	`%AppData%\Roaming\Komodo\VRSC\`

__*Usefull auxilairy Windows software:*__
Checksum utility:	https://raylin.wordpress.com/downloads/md5-sha-1-checksum-utility/
7-zip:			https://www.7-zip.org/

__*Procedure:*__
1) Make sure you have your seed phrase and password you use to log into your Lite mode wallet available.
2) First of all make a notition of your address and balance of VRSC you have in your wallet, before closing Agama.
3) Make sure the _latest_ version of Agama Wallet for Verus is installed.
	3a) Download the _latest_ Agama Verus Wallet from this location: https://veruscoin.io/.
	3b) Verify the SHA256 checksum of your download, so you have an untampered installer.
	3c) Run the file you just downloaded to install it.
4) Download the bootstrap from https://bootstrap.0x03.services/veruscoin/VRSC.html and verify the SHA256 checksum.
5) Unpack (using 7-zip when in Windows) the downloaded archive to *`Agama Wallet location`*.
6) Getting Agama ready for Native mode:
  6a) Start Agama and select **Native mode** VRSC.
  6b) You will get a red warning message about Zcash params. Dismiss it.
  6c) From the dropdown box, select `Z.cash` and click **Download**.
  6d) As soon as the download is finished, Agama will continu and bring you into your wallet. It will automatically start to synchronize the blockchain. Since we already put the majority of the chain in place, this will take just a few minutes.
9) Importing your existing Address:
  9a) Agama starts to synchronizing again, but this time it will be fast.
  9b) Click `Import Key`.
  9c) Enter your seed in the top field and click `Import`.
  9d) You get a *Wallet Notification: Address imported*. Dismiss it.
  9e) check if your Balance is correct.

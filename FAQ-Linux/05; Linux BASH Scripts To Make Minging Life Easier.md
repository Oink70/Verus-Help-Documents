LINUX BASH SCRIPTS TO MAKE MINING LIFE EASIER

Following are some bash scripts I wrote to help make managing your Linux-based CLI miner a bit easier.  Prereq is to install mailutils (postfix) and configure with your server's FQDN and set inet_interfaces=localhost in the postfix/main.cf file.

MINER SRVC MONITOR & ALERT IF DOWN
Checks for the komodod daemon and if it has stopped emails you.
```
#!/bin/bash

if pgrep -x "komodod" > /dev/null
then
    TRUE="1"
else
    echo "Merry Miner Has Stopped Mining!!! HELP!!" | mail -s "OUTAGE: Merry" -a "From: user@yourqualifieddomain.tld" you@youremail.tld
fi
```

ALERT ON NEW BLOCKS MINED
Prereq: Create a file called txHistory.txt and put 0 in it, saved to your home folder. The script then compares the current wallet TX count and compares to the txHistory file...so first run it will enter the right number in that file overwriting your 0.  Only emails you if the number changes.  I understand this is rudementary as other TXs would increase count, I'm working on a new more accurate script.
```
#!/bin/bash

historicalcount=$(cat /home/user/txHistory.txt)
livecount=$(/home/user/verus-cli/verus getwalletinfo | grep txcount | sed 's/[^0-9]*//g')

if (($livecount > $historicalcount))
then
    echo $livecount > /home/user/txHistory.txt
    echo "Merry Miner Has Mined a Total of $livecount Blocks! Woot!" | mail -s "Merry's Blocks: $livecount" -a "From: user@yourqualifieddomain.tld" you@youremail.tld
else
    NOCHANGE="1"
fi
```
WALLET BACKUP TO SECURED EMAIL (PROTONMAIL SUGGESTED)
For this script I recommend setting up a new Protonmail account with no association to any other service or your name, 2FA secure it.
```
echo "Attached Backup" | mail -s "Merry Backup" -A /home/user/.komodo/VRSC/wallet.dat -a "From: user@yourfullyqualifieddomain.tld" you@youremail.tld
Again, these scripts are a little rudementary but they do work! If you're curious my crontab, I'll post it next...to set your cron jobs use the command crontab -e
MY CRONTAB
In the following, the */5 is every 5 min, the 0 is on the hour every hour, the 0 12 is every day at 12 PM.
# m h  dom mon dow   command
*/5 * * * * /home/user/checkfornewblocks.sh
0 * * * * /home/user/checkifkomododisrunning.sh
0 12 * * * /home/user/backupwallet.sh
```
!!For any emails sent (for backup of dat file for example) make sure to enforce TLS security in postfix by adding the following line to your /etc/postfix/main.cf
```
smtp_tls_security_level=encrypt
```
(submitted by @J Oliver Westbrook):

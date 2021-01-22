---
title: "Secure & sovereign  Bitcoin in 25 Easy Steps"
---


Install Ubuntu (8 Steps)
========================

_I assume that you have access to an old windows laptop / desktop which you can use for this project. Before you begin make a backup of any files on your laptop / desktop because we are going to completely wipe your computer and install a fresh (secure) free operating system called Ubuntu._

1.  Plug in a 16GB (or larger) USB into your computer

2.  Go to [https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop) and download Ubuntu 19.10 (to your downloads folder) by clicking on the green button.
3.  Go to [https://www.balena.io/etcher/](https://www.balena.io/etcher/) and download Etcher for Windows (to your downloads folder) by clicking on the green button.
4.  Install and run Run Etcher. Click the ‘Select Image’ and click on the Ubuntu ISO file you downloaded, Then click Select Target and click on the USB you inserted, then click Flash.
5.  Turn off your computer and turn back on again. You should see an option to boot off the USB (you may need to press F2/F12 repeatedly while your computer boots up for this).
6.  Select install ubuntu, select `normal installation` enable both `Download updates` and `Install third-party software`.
7.  At the next screen select `Erase disk` & `Encrypt` and follow the rest of the install guide.
8.  Once installed, format the USB stick and rename it Bitcoin\_Backup

Install Bitcoin Core (17 Steps)
===============================

1. Launch Firefox (the icon is an orange circle), go to [https://bitcoincore.org/en/download/](https://bitcoincore.org/en/download/) and download latest release of bitcoin core by clicking the big blue button that says Download Bitcoin Core ([0.20.1](https://bitcoincore.org/bin/bitcoin-core-0.19.1/bitcoin-0.19.1-x86_64-linux-gnu.tar.gz)).

2.  Download the list of cryptographic checksums: [https://bitcoincore.org/bin/bitcoin-core-0.20.1/SHA256SUMS.asc](https://bitcoincore.org/bin/bitcoin-core-0.20.1/SHA256SUMS.asc)
3.  Open terminal (the icon is a black rectangle). You will need to run the following commands shown highlighted in grey. Enter them **exactly** as they are written (or easier, copy and paste the commands into the terminal to reduce the risk of making a mistake)
4.  Type `cd Downloads/`
5.  Type `sha256sum --ignore-missing --check SHA256SUMS.asc`
6.  Ignore any warnings and failures, but ensure the output lists “OK” after the name of the release file you downloaded. e.g. bitcoin-0.20.1-x86\_64-linux-gnu.tar.gz: OK
7.  Type `gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 01EA5486DE18A882D4C2684590C8019E36C2E964` It should output text saying that one key was imported, updated, has new signatures, or remained unchanged.
8.  Type `gpg --verify SHA256SUMS.asc`it should outupt text with a line starting `gpg: Good signature` & a complete line saying: `Primary key fingerprint: 01EA 5486 DE18 A882 D4C2 6845 90C8 019E 36C2 E964` . Should there be a warning saying that “key is not certified with a trusted signature” you should ask people you trust to confirm that the key fingerprint printed above belongs to the Bitcoin Core Project’s release signing key. This is beyond the scope of this guide.
9.  Type `tar xzf bitcoin-0.20.1-x86_64-linux-gnu.tar.gz`
10.  Type `sudo install -m 0755 -o root -g root -t /usr/local/bin bitcoin-0.20.1/bin/*`
11.  Type `/usr/local/bin/bitcoin-qt`
12.  Click OK. Bitcoin Core will download the bitcoin block chain. This step may take several days.
13.  In settings click encrypt wallet and enter a strong password (for example 4 random words e.g. correcthorsebatterystaple) make numerous copies of this password on paper and store them in various locations in your house. Ideally give additional copies of this password to trusted friend/family, you don’t need to tell then the details just put it in an envelope addressed to you and ask them if they can hold on to it because it’s very important that you don’t lose this password (or you’ll lose your bitcoin).
14.  Go to file, backup and save a backup to the memory stick you previously named ‘Bitcoin\_Backup’. Put this in an envelope clearly marked ‘IMPORTANT — PROPERTY OF XXX’ and store it somewhere safe in a different location to your laptop (e.g. a different room, or preferably a different building). Ideally do this multiple times.
15.  In settings enable coin control & change the default unit from whole bitcoins to sats (1/100,000,000th of a bitcoin) if that is more familiar.
16.  When you want to receive bitcoin click the Receive Tab and enter information about what you are going to receive for your own records in the LABEL data field (e.g. Test Withdrawal From Exchange XXX on 05JAN2020). If you know how much you want the invoice to be for you can enter an amount here. Click Create New Receiving Address.
17.  When you receive bitcoin it will appear in your transactions. When receiving bitcoin from someone you don't trust, always wait for 6 confirmations before deeming the transaction confirmed. Once you see 6 confirmations you can celebrate, you have received your first bitcoin without using a trusted third party — you are a secure and sovereign  bitcoiner.

_References: This guide was built using information from existing guides from the following sites:_
- [_https://bitcoin.org/en/full-node_](https://bitcoin.org/en/full-node#other-linux-gui)
- [_https://bitcoincore.org/_](https://bitcoincore.org/en/download/)

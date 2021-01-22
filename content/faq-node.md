---
title: "Node FAQ"
---

| By  6102bitcoin |
|:-:|

## Why run a node?
It is a private & secure way to use bitcoin.

## How do I run a node?
There are many ways, from downloading Bitcoin Core on your normal laptop right through to buying a dedicated device.
See [`my guide`](https://6102bitcoin.com/selecting-node-type/) for help selecting which method to use.

## I just want to run a node quickly!
By far the most frequently used bitcoin node software is **Bitcoin Core**.
Download [bitcoin core](https://bitcoincore.org/en/download/).
You should to verify that the file you download is authentic.

## How to verify
You need to verify that the file you download is actually bitcoin core and not a virus / malware.
You must use some software called PGP to do this as explained in [this guide](https://6102bitcoin.com/secure-bitcoin/).

## Waiting for initial sync
After you install Bitcoin Core you will need to leave it running for a few days for your node to be ready to use.
You will know it is ready when the progress bar at the bottom of the screen disappears.

## Bandwidth Use
Bitcoin core uses a lot of Bandwidth on setup, but not much after that.

## Storage Space
Bitcoin Core uses 300GB. If you have limited space you can turn on a setting called *Pruning* on installation which will store far less data.
Note that your node will still download ~300GB of data, but most of this data will not be stored.

## Coin Control
Turn on Coin Control in settings to allow you to maintain your privacy when using bitcoin.

## Encrypt Wallet
To make your wallet more secure add a password. Go to `Settings`/`Encrypt Wallet` and enter a strong (multi word with numbers & symbols) password and make a few notes of this password so you can't forget it.
If you forget the password you will lose your bitcoin.

## Receiving
Go to the receive tab, Add a label to an address and send the address to the person who is sending you bitcoin.
When someone sends bitcoin to the address you will get a notification on Bitcoin Core, although the transaction will be *unconfirmed*
After 6 confirmations (~1h) you can be confident that the bitcoin you have received is now in your control.

## Sending
Go to the send tab, select the coin you wish to spend, paste the address you wish to send to in the to field.
Set the fee (if you are not in a rush use a low fee) & click send.  

## Backup
Make a copy of the wallet.dat file by going to `File`/`Backup Wallet` and save in 3 places other then your computer (e.g. CD's, USB's, Portable Hard-drive).
Because you have encrypted the wallet you will need the password in order to restore from a backup, be sure to keep a number of backups of your password (ideally not right next to your backups of the wallet).

## Recovery
To recover instal bitcoin core and instead of making a new wallet paste your encrypted wallet.dat file in the following folder:
- Windows: `C:\Users\YourUserName\Appdata\Roaming\Bitcoin`
- Mac OS X: `~/Library/Application Support/Bitcoin/`
- Linux: `~/.bitcoin/.`

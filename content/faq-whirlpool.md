---
title: "Whirlpool FAQ"
---

Note: Many of these Q&A have been copied from real users, see footer for acknowledgements.

## Index
- [Overview](#overview)
- [Pre-Install](#pre-install)
	- [Who is behind Whirlpool?](#who-is-behind-whirlpool)
	- [What is Whirlpool?](#what-is-whirlpool)
- [Install](#install)
	- [How do I install Whirlpool?](#how-do-i-install-whirlpool)
	- [How do I connect Whirlpool to my own full node?](#how-do-i-connect-whirlpool-to-my-own-full-node)
	- [Paring](#pairing)
	- [Configurations](#configurations)
	- [Forgotten Passphrase?](#forgotten-passphrase)
	- [Do I need to run Tor?](#do-i-need-to-run-tor)
- [Deposit](#deposit)
	- [How to deposit](#how-to-deposit)
	- [Bitcoin in my Samourai Wallet isn't showing up in Whirlpool!](#bitcoin-in-my-samourai-wallet-isnt-showing-up-in-whirlpool)
	- [My wallet can't send to Bech32 addresses - what wallets can I use instead?](#my-wallet-cant-send-to-bech32-addresses---what-wallets-can-i-use-instead)
	- [Combining UTXO's](#combining-utxos)
- [Pre-Mix / Mixing](h#pre-mixing--mixing)
	- [How long does a mix take?](#how-long-does-a-mix-take)
	- [Do I need to leave my computer on?](#do-i-need-to-leave-my-computer-on)
	- [What are the fees?](#what-are-the-fees)
	- [How do to the fees compare to wasabi?](#how-do-to-the-fees-compare-to-wasabi)
	- [What is the Anonymity Set?](#what-is-the-anonymity-set)
	- [Which pool should I use?](#which-pool-should-i-use)
	- [Will there be more pools?](#will-there-be-more-pools)
	- [Can I mix more than the pool minimum?](#can-i-mix-more-than-the-pool-minimum)
	- [How do I join a pool?](#how-do-i-join-a-pool)
	- [It's not mixing!](#its-not-mixing)
	- [Priority](#priority)
- [Post-Mix](#post-mix)
	- [What do I do now?](#what-do-i-do-now)
	- [How do I spend?](#how-do-i-spend)
	- [Post-Mix Spending Fees](#post-mix-spending-fees)
	- [Where does the change go?](#where-does-the-change-go)
	- [STONEWALL](#stonewall)
	- [STONEWALLx2](#stonewallx2)
	- [STOWAWAY](#stowaway)
	- [Ricochet](#ricochet)
	- [Sending to another Samourai Wallet user](#sending-to-another-samourai-wallet-user)
	- [Am I safe to send my mixed coins to my hardware wallet?](#am-i-safe-to-send-my-mixed-coins-to-my-hardware-wallet)
	- [I want to send to my hardware wallet!](#i-want-to-send-to-my-hardware-wallet)
	- [I want to spend my coins at a third party service!](#i-want-to-spend-my-coins-at-a-third-party-service)
	- [Can I recombine my mixed coins?](#can-i-recombine-my-mixed-coins)
	- [What do I do with the unmixed change?](#what-do-i-do-with-the-unmixed-change)
	- [History of spent coins](#history-of-spent-coins)
	- [Balance on Samourai Wallet is still 0!](#balance-on-samourai-wallet-is-still-0)
	- [Locked funds, need to recover!](#locked-funds-need-to-recover)
- [Meta](#meta)
	- [Does Samourai Wallet have a warrant canary?](#does-samourai-wallet-have-a-warrant-canary)
	- [Do I need to 'trust' the Whirlpool Server?](#do-i-need-to-trust-the-whirlpool-server)
- [Errors](#errors)
	- [Thread 1 Idle](thread-1-idle)
	- [Error spawn java ENOENT](#error-spawn-java-enoent)
	- [MIX:ERROR](#mixerror)
- [Acknowledgements](#acknowledgements)

# Overview

The general overview is install whirlpool, connect to Samourai Wallet, deposit bitcoin, mix, spend from samourai wallet.

There are a few short [video guides](https://www.youtube.com/watch?v=0FiIGhi3_R0&list=PLIBmWVGQhizIWHyDkY-AzYc-Rn_3zGRct) produced by the developers which are very useful for some of these steps.

The [official whirlpool guides](https://support.samourai.io/section/38-whirlpool) are important to read, though I have included some of that content below.

# Pre-Install

### Who is behind Whirlpool?

The Company that is developing Whirlpool is [Katana Cryptographic](https://katanacrypto.com/) who are best known for developing [Samourai Wallet](https://samouraiwallet.com/) - a superb mobile (currently android only) bitcoin wallet.

### What is Whirlpool?

Whirlpool is a collection of tools which can be used to improve privacy when using bitcoin. You deposit bitcoin (which may be directly linked to your identity if you bought from an exchange for example) and after using the tools available you can send the bitcoin without leaking information about your past transactions.

Importantly, throughout this process you retain full ownership of the bitcoin (you aren't trusting anyone with your funds at any time).

Another important thing to highlight is that Whirlpool is currently in 'PUBLIC BETA' which means it is not a finished product and as such you may experience some slight hiccups (though my experience was very smooth), particularly if you are using unusual hardware / an untested OS. Be patient, read this FAQ. If you have further questions ask on the [telegram channel](https://t.me/whirlpool_trollbox) and if all else fails you can [contact support](support@samouraiwallet.com).

# Install

### How do I install Whirlpool?

You need to install whirlpool & Samourai Wallet.

### Install Whirlpool (To mix bitcoin)

#### Summary
You currently need to [download](https://github.com/Samourai-Wallet/whirlpool-gui/releases/latest) and run the latest whirlpool release on a computer (Windows/OSX/Linux), note an android app is being internally tested.
Note that you need to [install JAVA](https://openjdk.java.net/).

#### Step by Step for Linux (debian distros)

1. Downloaded tar.gz from [latest releases](https://github.com/Samourai-Wallet/whirlpool-gui/releases/latest)
2. Extracted to folder
3. Install java from command line `sudo apt install openjdk-8-jre-headless`
4. Check it installed with `java -version` which should return something like `openjdk version "1.8.0_212"`
5. Install npm `sudo apt-get install npm`
6. Install yarn `sudo npm install -g yarn`
7. Update `sudo apt-get update`
8. Restart
9. Open command line from the whirlpool-GUI folder
10. `yarn` (takes 2 mins)
11. `yarn package`
12. Double click app image
13. Try standalone GUI
14. Enable TOR
15. Paste pairing text & then later your passphrase
16. Deposit into wallet (doesn't auto close)
17. Wait for confirmation
18. Click "Tx0"
19. Set miner fee, pool & mixs target
20. UTXO is split and mix is ready to begin.
21. Wait for confirmation.
22. UTXO Appears in post-mix

### Install Samourai Wallet (To send bitcoin)
You need to [download](https://play.google.com/store/apps/details?id=com.samourai.wallet) Samourai Wallet, currently available only on Android.

*note: It is possible to emulate the app if you do not have an android device*

A direct APK download will be available on the website only after 1.0 release. If you require it now, you either need to compile it yourself or download from [google play](https://play.google.com/store/apps/details?id=com.samourai.wallet).

### How do I connect Whirlpool to my own full node?

You need to run DOJO to connect Whirlpool to your own node. Dojo is another free piece of software produced by the developers of Samourai Wallet. This is not yet possible but **will be possible soon**.

You do **NOT** need DOJO to try out whirlpool, but the Samourai Wallet server knows your xpubs (your public keys) if you do not run DOJO. Thus, it is better to run DOJO when mixing and **this will be possible in the future (remember, whirlpool is currently in `PUBLIC BETA`).**

### Pairing
Once you have whirlpool installed & Samourai Wallet installed you must 'pair' these tools so that they can access your bitcoin. This is done by copying a `paring string` from the Samourai Wallet app into the Whirlpool GUI.

It is very important **that you do this securely**; this paring string includes your mnemonic (from which all your bitcoin private keys are calculated).
The mnemonic is encrypted with your passphrase, but it is still important to transmit it securely.

Read the [full pairing guide](https://support.samourai.io/article/76-pairing-samourai-wallet-to-whirlpool-desktop).

### Configurations

There are [detailed configuration options](https://support.samourai.io/article/77-understanding-whirlpool-desktop-configuration-options) which can be explored, though this is not nececcary.

### Forgotten Passphrase?

If you go to your Samourai Wallet and navigate to Settings > Troubleshooting > Test passphrase/backup - You can try different passphrases without risk. It will tell you when correct or incorrect.

If you can't remember your passphrase you can also create a new wallet, **but you must send any BTC from the old wallet first!**

### Do I need to run Tor?

All whirlpool network traffic can be set to go via Tor; you will see this clearly when setting up whirlpool.

# Deposit

The deposit 'account' consists of all the bech32 UTXOs within your standard Samourai Wallet. UTXOs in this account have not been cycled through Whirlpool yet. You can receive deposits directly into this account or select UTXOs from this account to cycle.

### How to deposit

#### Deposit from an external wallet:

If you do not have any UTXOs in your Samourai Wallet, you can generate a deposit address for your wallet by pressing the red `+Deposit` button within the desktop client. Once the deposited funds have received one confirmation they will be ready to be cycled.

#### Choose UTXO(s) from your Samourai Wallet:

Within the Desktop Client navigate to the Deposit tab directly under `Last Activity` on the left hand side of the screen. The Deposit account contains all the bech32 UTXOs in your paired Samourai Wallet. Once the deposit tab has been selected a list of your bech32 UTXOs in Samourai Wallet will be displayed.

### Bitcoin in my Samourai Wallet isn't showing up in Whirlpool!

Whirlpool uses Bech32 addresses only. Bitcoin in other addresses won't be visible from within whirlpool.
If you want to move bitcoin into Whirlpool you need to send it to a new bech32 address (i.e. deposit into whirlpool).

### My wallet can't send to Bech32 addresses - what wallets can I use instead?

Whirlpool generates Bech32 addresses only. These addresses start with the characters bc1... Some wallets/exchanges don't yet support this type of address and my give an error message (e.g. "unknown bitcoin address"). The solution is to manage your funds with a wallet which does support Bech32.

Of [the wallets](https://en.bitcoin.it/wiki/Bech32_adoption) that support Bech32, only the following wallets have Coin Control;

| Platform 						| Recommended 																					| Other										|
| ---------						| -----------------------------------------------------	|------------------------	|
| Mobile (Android)		| [Samourai](https://play.google.com/store/apps/details?id=com.samourai.wallet)								| [Electrum](https://play.google.com/store/apps/details?id=org.electrum.electrum)								|
| Desktop 						| [Bitcoin Core](https://bitcoincore.org/en/download/)	| [Electrum](https://electrum.org)	|

While fees are low it is easiest to simply send your bitcoin from your old wallet to a new [Samourai Wallet](https://play.google.com/store/apps/details?id=com.samourai.wallet). Alternately you could sweep the funds using one of the wallets in the table.

Be careful. If you send all your coins from an old wallet to a new wallet (from the table above) in one transaction then you will merge all your coins which is bad for privacy. If it is practical, **import your seed into one of the wallets in the table.**

### Combining UTXO's
You must have a single UTXO with a balance larger than the pool size (i.e. a 0.02 BTC UTXO to use the 0.01 BTC Pool). If you have multiple smaller UTXO's which are cumulatively sufficient (i.e. 3 0.005 BTC UTXO's) you could combine them in order to mix.

Note that doing so is bad for privacy and you could be damaging your privacy by linking past actions to coins which are 'tainted'. It is better to wait for smaller pools than mix coins which are from different sources.

If the coins you are mixing have come **directly** from the same source (i.e. a tipping service) there is no loss of privacy in recombining them.

# Pre-Mixing / Mixing

This 'account' consists of all the UTXOs that are prepared to cycle but are still pending. UTXOs will remain in Premix until they have one confirmation and they are selected in a Whirlpool cycle. These UTXOs cannot be spent yet but will have priority in any Whirlpool cycle over UTXOs in the Postmix Account.

### How long does a mix take?

The actual process takes seconds, what takes time is waiting for other users to get on.
pre-mix is faster than post-mix.

### Do I need to leave my computer on?

Yes, whirlpool must be running to keep mixing.

### What are the fees?

Whirlpool is different than other CoinJoin services, in that you do not pay a volume based fee per anonymity set, but instead you pay a one time flat fee for an unlimited anonymity set.

To put it simply, it costs the same in Pool Fees to cycle 1 BTC or 1000 BTC. Once the pool fee is paid, it costs nothing to continue cycling. With each cycle you gain a greater privacy advantage with a deeper anonymity set.

You currently pay a one-off fee of 5% of the pool fee to start mixing a bitcoin UTXO (the Tx0). As long as you leave the UTXO in the mix your Anonymity set will increase at no additional cost. Note, this is 5% of the pool denomination not 5% of the amount being mixed, so 0.05 BTC pool is 0.0025 BTC fee regardless of how much is being mixed & 0.01 BTC pool is 0.0005 BTC fee.

The more you mix and the longer you stay in pool the cheaper whirlpool becomes (relative to other mixing tools). Whirlpool can be expensive if you are mixing in a pool denomination that is too large for the amount you're mixing.

As mempool clears down, miner fees drop so time your Tx0 if you can.

Once you pay your mix fee you should always wait for the mix to complete. In an emergency when you need to spend a UTXO which is in pre-mix you can manually generate the pre-mix private key (samourai, settings, Troubleshoot, address calculator, pre-mix, display private key) but you will have wasted the mix fee.

### How do to the fees compare to wasabi?

In terms of fees paid to use the mixing services:

| Characteristic | Whirlpool                                | Wasabi                             |
| -------------- | ---------------                          | ---------------------------------- |
| Pool Size      | 0.05 & 0.01                              | 0.1                                |
| Fee            | 5% * pool size                          | 0.003% * Anonymity Set * mixed amount |

Please note, this does not include on-chain fees.

**More Fee Info**

**Whirlpool:**

The fixed fee pays for entry into the mix, there is no additional fee to remain in the mix, thus the marginal cost of increasing the Anonymity Set of the UTXO is zero (described as 'free-riding' in the mix).

**Wasabi:**

Users pay more to gain more privacy, but can choose to have less at lower cost.

### What is the Anonymity Set?

The anonymity set is effectively the size of the group you are hiding in.

Currently 5 people take part in a Whirlpool CoinJoin producing 5 output UTXO's each with an anonymity set of 5 per mix.

Take care when estimating the anonymity set of coins. The anonymity set of a single mixing round is meaningful, scaling the number of rounds with the anonymity set per round gives a less meaningful number, especially while the number of unique users is low at this early stage of adoption.

### Which pool should I use?

The denomination of the pool determines the minimum amount you can cycle through that pool and the resulting denomination of the newly cycled UTXOs in your wallet.  Generally the larger the UTXO you are cycling, the larger the pool you want to choose.

You should choose a pool size based on a few things,

1. The amount being mixed, you obviously don't want to mix 0.06 in the 0.05 pool, as you will be paying about 5% in fees, the 0.01 pool would be more cost effective. That being said mixing 10 BTC in a small pool would be very cheap on a pool fee level, but you would make up for it in miner fees paid.
2. The amount that you normally spend. It is nice to have varying sized post-mix UTXO's. Ideally lower denomination than your usual spending amount, but not dramatically lower. This is useful for spending those post-mix coins. Where you basically want to make sure you are using a Cahoots spend for additional mixing "on the way out" and if you can't do that, produce as little post-mix change as possible with the consumption of a single UTXO per spend.

### Will there be more pools?

It very easy for the developers to create new pools but they don't want to fracture the liquidity too early. Both the 0.01 & 0.05 pools are still finding their feet right now. Going forwards a 0.005 & a 0.5 BTC pool may be introduced.

### Can I mix more than the pool minimum? ###

Yes.
In the 0.01 BTC Pool you can deposit 1 BTC which will be split into 100 separate UTXO's. The cost is the same as mixing in the 0.05 BTC pool but in this pool the bitcoin will be split into 20 UTXO's.

### How do I join a pool?

With the `Deposit` tab selected, you will see a list of bech32 UTXOs available on the right hand side of the screen

1. Press the red Tx0 button on the far right side of a confirmed UTXO to open the pool selection screen
2. Select a miner fee profile, the higher you pay in miner fees the quicker your UTXOs will confirm, and the quicker your cycle will complete.
3. Select a pool, you generally want to choose the largest pool you can based on the amount of the UTXO you are cycling.
4. Select a target number of cycle, this can be left as 1 as you can later cycle these UTXOs manually. If you set a number higher than 1 the UTXOs will be cycled automatically until they reach the target.
5. Press the red Tx0 button on the bottom of the pop up modal to begin the process.

### It's not mixing!

This is still a BETA, adoption is low at the moment meaning mixing is happening slowly. It is possible that there are mixes but that you have been unlucky and not randomly selected. As adoption grows this issue will disappear. See the [Errors section](#Errors) if you have any displayed errors.

### Priority

Fee payers are always given priority, post-mixers need to be randomly selected. There are more post-mixers than pre-mixers, so pre-mixing is quicker.

# Post-Mix

This 'account' consists of all the UTXOs that have completed at least one cycle. These UTXOs are available for spending from within Samourai Wallet or available to cycle again for greater privacy.

### What do I do now?
If you have a post-mix UTXO you can spend it, or once all your pre-mix are done, you can remix them.

Whirlpool has been designed with extensive privacy enhancing strategies that help make sure you do not undo the privacy gains of Whirlpool when you go to spend your UTXOs.

It is advised that you keep your funds within Whirlpool and directly spend using your Samourai Wallet on an as needed basis. This will allow you to take advantage of our superior coin selection and post mix spending tools, making it very hard to accidentally undo the privacy gains of Whirlpool.

### How do I spend?

To spend from post-mix whirlpool go to Samourai Wallet, go to the ☰ icon at the top right -> "spend from post-mix Whirlpool". You can then press ☰ again and click "Show unspent outputs" (once inside the "Spend from post-mix whirlpool" menu) to see all your UTXOs.

### Post-Mix Spending Fees

None of the post-mix spending costs any additional fees.

### Where does the change go?

UI on mobile has not been fully implemented. The change outputs went back to the post-mix account. If you load up your Whirlpool Desktop GUI you will see them in the post-mix tab, they will be greyed out. It is still "mixed", spending doesn't unmix it, especially if spent via STONEWALL at least.

From the post-mix spend screen in Samourai you can view the UTXO list, and reveal the private keys for those change UTXOs. Additionally you can calculate the private keys for all your addresses (including whirlpool pre-mix and post-mix) from the Address Calculator in Settings > Troubleshooting.

### STONEWALL

There is no additional fee for [STONEWALL](https://support.samourai.io/article/64-what-is-stonewall) - it is recommended on the post-mix because it creates additional confusion/entropy. Like a CoinJoin you cannot determine the input and output owners - and this is especially recommended if you plan on sending to cold storage (aka not spending) as you will not degrade the entropy over time.

You should *always* try for at least a STONEWALL when spending from the post-mix screen (or spend the entire UTXO).

If you try to spend without stonewall you will get the following error warning:
"Spending from your post-mix account without using STONEWALL will result in a loss of privacy gained through Whirlpool. Post-mix consolidated coins should be cycled through whirlpool to regain lost privacy."

### STONEWALLx2

Better than a simple STONEWALL, with a [STONEWALLx2](https://support.samourai.io/article/74-how-to-create-a-stonewallx2-transaction) you work with a friend to add more confusion into the on-chain transaction.  

### STOWAWAY

A [stowaway](https://support.samourai.io/article/73-creating-a-stowaway-transaction) creates a transaction that looks like an ordinary transaction, but is actually a mini CoinJoin with your friend. So while it looks normal, it really isn't. The amount spent isn't known, and the ownership of inputs to outputs isn't actually known.

### Ricochet

From the Spend From post-mix screen in the Samourai Wallet you cannot do a ricochet yet. If you wanted to do a [Ricochet](https://support.samourai.io/article/14-making-your-first-ricochet-send) you would first need to sweep to your main Samourai Wallet account.
This will incur an additional fee which is clearly displayed in the sending process.

### Sending to another Samourai Wallet user

Sending to another Samourai Wallet user is the same as sending to any bitcoin address and the same privacy rules apply. However, some additional Post Mix spending tools are available only between Samourai Wallet users. An example of this is Stowaway, which is a CoinJoin with a trusted friend that doesn't look like a CoinJoin and masks the true amount spent on the blockchain.

### Am I safe to send my mixed coins to my hardware wallet?

The post-mix spending tools built into Whirlpool/Samourai Wallet are second to none. It is generally advisable that you keep mixed UTXO's in the post-mix to keep mixing (for free) and then spend with the best in class tools within Samourai Wallet when needed.

### I want to send to my hardware wallet!

#### **DO NOT:**
- Spend the entire balance in Whirlpool Postmix to a single address on your wallet / cold storage device. This is known as merging inputs and completely undoes the privacy gains provided by Whirlpool.  
- Use the Default Hardware Wallet Software
Most hardware wallets communicate with servers to provide you with your balance. This reveals your public key to the server, which damages your privacy - the hardware company can now theoretically link together all your addresses. As a result **it is not recommended** that you send your mixed coins to an address associated with your hardware wallet unless you are confident that you have set up your hardware wallet in a way that it does not communicate with a 3rd party server (see below).

#### **DO:**
- Use your hardware wallet with Electrum, which connects to your Bitcoin Core through [Electrum Personal Server](https://github.com/chris-belcher/electrum-personal-server).
- Wait until post-mix is done, and then spend from the post-mix spend screen - If you are sending less than half of your post-mix balance the wallet will automatically turn on STONEWALL. If the wallet cannot turn it on it will warn you that it cannot, in this case you can then send each UTXO, one by one into your hardware wallet, ideally not all at the same time (leave a random multi hour delay between sweeps) and not all with the same fee rate.

### I want to spend my coins at a third party service!

Navigate to the PostMix Send Screen in your Samourai Wallet and create a transaction as you normally would. If it is possible your wallet will enable STONEWALL automatically - this will provide you with additional entropy and is considered the minimum requirement for sending from your PostMix balance with minimal privacy loss.

If a STONEWALL cannot be created your wallet will warn you before sending. Please follow the guidelines below if you are unable to activate STONEWALL.

#### **DO NOT:**
- Ignore the warning. If STONEWALL cannot be activated, it means you are going to degrade your privacy and the privacy of your counterparts involved in the cycle.

#### **DO:**
- Spend a smaller amount. STONEWALL activates when spending less than half of your available balance.
- Add more UTXOs to your Whirlpool wallet so that the amount you need to spend is less than half of your available balance.
- Enlist the help of a friend to create a STONEWALLx2 transaction. This is very much like a normal STONEWALL but you are using a trusted friends UTXOs in addition to your own. This has the added benefit of additional mixing within the spend transaction and you can spend more than half of your available balance.

### Can I recombine my mixed coins?

It is advisable to limit the recombining of mixed coins because it can only decrease the privacy of said coins. This links all the consolidated UTXOs in one transaction, creating only one output, which then clearly controls all these funds. As a result it is best not to recombine your mixed change.

That said, be aware that the fee required to spend multiple UTXO's is higher than the fee required to spend a single UTXO, for this reason you should use the largest pool possible when mixing funds (don't split a 1 BTC UTXO into 100 separate 0.01 BTC UTXO's).

### What do I do with the unmixed change?

There are no hard and fast rules for what to do with the change. It is important to note that the change may be linked to your identity and should be treated as a kind of toxic waste (handled with great care).

**Warning!**

You want to avoid mixing change coins together where possible. If you mix change you will **decrease your privacy** because the transactions that created the change will now be linked. Note that this is also true if you mix your change with a mixed coin.

It is very important that you don't send different coins to the same receiving address (even if performed as separate transactions) as this will also link the coins together, damaging your privacy.

**Your Options**
- Wait for a smaller pool to be made by the developers.
- If you don't care about linking the history of the coins because they are all from the same source then you could combine them and then mix.  
- Mix with [Joinmarket](https://github.com/JoinMarket-Org/joinmarket-clientserver).
- Donate them (e.g. [to the EFF](https://www.eff.org/))
- Spend them on something that isn't a particular privacy risk (eg. gift cards).
- Open a lightning channel (note opening large number of public channels could link your change together).
- The ultimate solution is to 'close the loop' i.e. spend a change coin without merging it with other coins don't generate it in the first place by sending whole coins.

### History of spent coins

Select the UTXO list from the post-mix spend screen and look at the tx of the UTXO you need to follow.

### Balance on Samourai Wallet is still 0!

The balance on Android only shows the account 0 balance (your normal Samourai balance). Neither pre-mix or post-mix display in the android wallet. All you can do with Android wallet right now is spend from your post-mix account

### Locked funds, need to recover!

You can generate the private keys used for all of the above steps from within samourai if anything goes wrong `settings -> Troubleshoot -> Address calculator -> Post mix -> display private key`

If for some reason you don't want to use samourai you can use electrum, which should only be downloaded from this url: [https://electrum.org/#download](https://electrum.org/#download)

Do not use any version before 3.3.4

- Provide a name for your Electrum wallet
- Standard Wallet
- 'I already have a seed'
- Click 'Options'
- Check both 'Extend this seed with custom words' and 'BIP39 seed'. Ignore BIP39 warning.
- Enter your 12-word mnemonic
- Enter your BIP39 passphrase on the 'Seed extension' screen
- Type of addresses: 'native segwit (p2wpkh)'
- Override suggested derivation path with: m/84'/0'/2147483646' (do not omit trailing ' character)
- Provide a password. You will need this password to open your wallet whenever you use Electrum.

Electrum might take a long time to sync. They are experiencing ongoing DDOS attacks. If syncing takes too long, select the Network Tool and see how many nodes you are connected to. Changing the default server can sometimes help: right-click the server in the list and click 'use as server'

# Meta

### Does Samourai Wallet have a warrant canary?

The nature of Whirlpool is that you shouldn't need to trust the devs or the coordinating server, as you can verify that the code doesn't leak information to anyone. That said, there is a [warrant canary](https://samouraiwallet.com/canary).

### Do I need to 'trust' the Whirlpool Server?

If you connect your samourai wallet & whirlpool to your own DOJO (software which serves you information from your own node) then the only known possible 'malicious' actions that the server *could* perform are two sides of the same coin;
- blacklisted UTXO's
Though this would not affect the users who are able to successfully mix with other 'honest/real' peers. Note that whirlpool will will ban for consistent repeated drop outs.
- Sybil Attack
The follow-up concern is the inverse of the above. It is possible that the server could *only* include one 'honest/real' coin in the mix and supply the other coins themselves. This would give a false sense of security, **but it would not worsen the existing privacy of the coin**.
If multiple chain-analysis companies attempt to flood the whirlpool mix (to decrease the true anonymity set) they will hinder each other's efforts (unless they are cooperating).

# Errors

### Thread 1 Idle

If your transactions have not confirmed the client won't be doing anything and may give this warning.
To resolve this wait for the confirmations to confirm.

If you have disabled automix or stopped the client just start again (click start in the top right).

### Error spawn java ENOENT
Make sure Java is installed on your device and is correctly included in your PATH.

### MIX:ERROR
A mix can fail for a number of reasons, and doesn't indicate that anything is wrong with your particular configuration.  Under default configuration UTXOs that have failed should automatically be queued after a short period of time. If they don't you can feel free to restart them manually by pressing the "mix" button

# Acknowledgements

Thanks to the developers of Whirlpool.

Thanks to the following people for the help that they have provided to whirlpool users on the whirlpool telegram group which I have condensed into this FAQ.
- [Nicholas](https://github.com/Technifocal)
- [Samourai Wallet](https://twitter.com/SamouraiWallet)
- [Samourai Dev](https://twitter.com/SamouraiDev)
- [Ketominer](https://twitter.com/ketominer)

Thanks also to those who made contributions to my [Wasabi FAQ](https://github.com/zkSNACKs/WalletWasabi/blob/master/WalletWasabi.Documentation/FAQ.md) - some overlapping content has been copied over, I believe it is all from my original work.

Please issue pull requests if you have suggestions.

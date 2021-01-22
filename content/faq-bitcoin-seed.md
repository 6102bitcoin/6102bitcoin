---
title: "Bitcoin Seed FAQ"
---

## Index

1) [**The Basics**](#1-The-Basics)
	- [Introduction](#Introduction)
	- [Terminology](#Terminology)
	- [What is a HD Wallet?](#What-is-a-HD-Wallet)
2) [**Creating your seed**](#2-Creating-your-seed)
	- [Where should I physically be when I backup my seed?](#Where-should-I-physically-be-when-I-backup-my-seed)
	- [All seeds are not created equal](#All-seeds-are-not-created-equal)
	- [Does the order of the words matter?](#Does-the-order-of-the-words-matter)
	- [How do I get my seed?](#How-do-I-get-my-seed)
	- [Should I check my seed?](#Should-I-check-my-seed)
3) [**Storing your Seed**](#3-Storing-your-Seed)
	- [Why should I bother storing my seed, I only have a small amount of bitcoin?](#Why-should-I-bother-storing-my-seed-I-only-have-a-small-amount-of-bitcoin)
	- [Should I have multiple (redundant) backups?](#should-i-have-multiple-redundant-backups-of-my-seed)
	- [Paper Backups](#paper-backups)
	- [Metal Backups](#metal-backups)
	- [How can I store my seed](#How-can-I-store-my-seed)
	- [Can I 'encrypt' my seed so that all is not lost if someone finds my mnemonic?](#Can-I-encrypt-my-seed-so-that-all-is-not-lost-if-someone-finds-my-mnemonic)
	- [Passphrases](#1-use-a-passphrase-alongside-your-mnemonic-seed-following-bip39)
	- [Encrypt Seed Words](#encrypt-the-plaintext-seed-words)
	- [Should I split my mnemonic in two (short version)?](#should-i-split-my-mnemonic-in-two-short-version)
	- [Should I split my mnemonic in two (long version)?](#should-i-split-my-mnemonic-in-two-long-version)
	- [Should I split my seed ABC into AB|BC|CA?](#should-i-split-my-seed-abc-into-abbcca)

4) [**Using your Seed**](#4-Using-your-Seed)
	- [Can I recover my bitcoin without my seed?](#Can-I-recover-my-bitcoin-without-my-seed)
	- [Can I recover my bitcoin without my passphrase?](#Can-I-recover-my-bitcoin-without-my-passphrase)
	- [I have forgotten my passphrase, what now?](#I-have-forgotten-my-passphrase-what-now)
	- [How should I recover bitcoin using my seed?](#How-should-I-recover-bitcoin-using-my-seed)
	- [What is the Derivation Path?](#What-is-the-Derivation-Path)
	- [How often should I check backups?](#how-often-should-i-check-backups)

# 1) The Basics

### Introduction

Great - you have decided to control your bitcoin directly instead of using a custodial service like an exchange. This is a very wise move - exchanges fall into only two categories; those which have been hacked and those which will be hacked.

By holding your own keys, you (and only you) are able to spend your bitcoin. You should take time to read this FAQ in order to understand the common errors & mistakes, and to learn the best practice in seed management. Be aware that this a general guideline. Every solution for storing your bitcoin seed will be a tradeoff between security and usability, and the level of security needed or wanted will vary from person to person, as will the threats you are trying to secure yourself against.

### Terminology

When it comes to bitcoin seed descriptions, words are often confused and used interchangeably. It is important that we speak a common language, so let me define what I mean by each of these words.

| Word | Definition | Other Names |
| ---- | ---- | ---- |
| [**Private Key**](https://en.bitcoin.it/wiki/Private_key) | A secret 256 bit number that you use to spend bitcoin | Secret Key |
| [**Seed**](https://en.bitcoin.it/wiki/Seed_phrase) | A 256 bit number which can be used to generate a bitcoin private key. |  |
| **Mnemonic Seed** | The seed encoded in the form of a list of words in a specific order.  | Mnemonic / Seed Phrase / Seed Words |
| **Non-Extended Mnemonic** | 12/24 Words (Just the Mnemonic) | Mnemonic  |
| **Extended Mnemonic** | Mnemonic (12/24 words) + Passphrase | Extended Seed |
| **Backup** | A complete set of information from which your bitcoin can be recovered  | |
| **Encrypted Backup** | Backup encrypted with a password (not to be confused with a passphrase) | |

### What is a HD Wallet?

In practice, most bitcoin wallets are 'HD' (Hierarchical Deterministic) wallets - This means that a single bitcoin private key is used to generate as many key pairs as is required. This makes it easy for the user to use a new address each time they receive bitcoin, which is how bitcoin is designed to be used.

With a HD wallet the bitcoin private key (which is derived from the seed) is combined with a 'chain code' to generate what is referred  to as a 'master extended key'. For more details see [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki).

Typically when backing up a wallet you are presented with the mnemonic seed - a series of either 12 or 24 words from [this list](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt) - it is an encoded version of your seed made to be easy to read and transcribe. The encoding method is detailed in [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki#), but effectively each word on the wordlist corresponds with a number, and thus your 12 or 24 word mnemonic seed is simply an easy to write representation of a large number (your seed).

Many wallets carelessly label the mnemonic seed as just the 'seed' - take care, the mnemonic seed can be extended with an additional word or sentence (a passphrase), without which you cannot decode the actual seed (a 256 bit number) and thus, you cannot recover your bitcoin.

##### Important Note:

Anyone with access to your seed can spend your coins. As such it is imperative that you store copies of your seed securely. The next section explains how to do just that.

# 2) Creating your Seed

### Where should I physically be when I backup my seed?

Remember that if anyone sees your seed it is potentially compromised, and should be treated as such.
For this reason make sure that you backup your seed somewhere that is private and that has no cameras/CCTV.
- Don't read your seed aloud as someone could hear it.
- Don't type it into a computer
- Don't take a picture / screenshot

### All seeds are not created equal

Suppose you have a computer riddled with malware and viruses and you download some bitcoin wallet software and view the seed (or more likely the mnemonic seed). This seed is likely insecure. The viruses/malware may be taking screenshots of your computer at regular intervals and sending this data to the creator of the virus/malware.
If you can see your seed on screen, then potentially so can the hacker.

For this reason, with non-trivial amounts of bitcoin it is crucial that you carefully control the environment in which the seed is generated. The easiest way for non-technical people to do this is to buy a 'Hardware Wallet'. These devices store all the 'secret information' required to access your bitcoin on the dedicated hardware device so that it doesn't matter if your computer has viruses/malware.

That said, some hardware wallets are better than others so make sure that you never enter your seed into your computer - only enter it into the device itself.

Another option is to generate a seed using a clean computer which is not connected to the Internet.

### Does the order of the words matter?
Yes! The order of the words in a mnemonic seed does matter. You must store your mnemonic seed in such a way that the order of the words is clear and unambiguous. Remember - the mnemonic seed is simply an encoding of the seed which is a large number, if you get the order wrong then you will decode a different number.

### How do I get my seed?

This will depend on the bitcoin wallet that you are using. Most have a 'backup seed' option visible in the settings menu which can be used at any time, though some only allow seed backups when the wallet is initialised. Again, what you are backing up is typically the mnemonic seed. If you use an extended mnemonic (i.e. A 12/24 word mnemonic seed + a passphrase) you MUST have access to the passphrase to recover your bitcoin. For this reason it is very important to backup your passphrase in addition to your seed - though you should not store them in the same place.

It is important to note that it is generally insecure to create your own seed as humans are not good at creating truly random information.

### Should I check my seed?

You should definitely check your backup as part of your process for backing up. Failure to do so could lead to you losing your bitcoin - don't risk it. Part of checking the backup is checking that you have correctly recorded your seed, though this is not the whole process. You should additionally check that you know the derivation path and the passphrase (if you used one).

# 3) Storing your Seed

### Why should I bother storing my seed, I only have a small amount of bitcoin.

The value of bitcoin could increase substantially and you may one day regret not backing up your seed. You should **always** back up your seed. It is good practice to regularly review your seed management and consider how effective your chosen solution is.

### Should I have multiple (redundant) backups of my seed?

Yes. For the reasons explained below you should have multiple redundant backups of your seed.

### Paper Backups

If you do decide to use a paper backup:
- Use waterproof ink & paper
- Write on a hard surface so you don't indent the paper below
- You can increase the durability of your paper backup by laminating it
- Consider labelling your seed discreetly. Something labelled 'BITCOIN SEED' is more likely to be swept (stolen) than if you label it 'COOKIE RECIPE', though it may be easy to forget that you did this.
- Laminate the paper

Learn More: [Here](https://www.quora.com/How-do-I-maintain-a-paper-notebook-that-can-remain-for-years) and [Here](https://www.quora.com/If-I-write-with-a-pencil-on-my-notebook-will-the-writing-last-for-a-long-time-say-50-years-or-will-it-just-fade-away-gradually)

### Metal Backups

There are lots of options available. See Lopp's [initial comparison](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-21f47cf8e6f5) & [more recent comparison](https://youtu.be/zFN__b6ARH4?t=20593).
The [Blockplate 1.0](https://www.blockplate.com/) appears to hold up well to fire / crushing while being easy to use.

### How can I store my seed?
Initially let us consider the case where you store a single unencrypted mnemonic seed (12 or 24 words).

| Method  						   	|Location          				| Digital Theft Resistance 	| Physical Theft Resistance 		| Durability 						|
| ------    					    | ---- 				    		| -------------------------	| ------------------------------|	---------------				|
| Screenshot              | On Phone 					  | Weak							        | Weak													|	Fragile (Deletion) 		|
| Notes App               | On Phone					  | Weak							        | Weak													|	Fragile (Deletion)		|
| Printed Paper Note  		| In Home 					  | Weak							        | Weak													|	Fragile (Fire)	  		|
| Printed Paper Note 			| Bank Deposit Box 		| Weak							        | **Strong** \[3]								|	**Durable**        		|
| Handwritten Paper Note  | In Home 					  | **Strong**				        | Weak													|	Fragile (Fire)	  		|
| Handwritten Paper Note  | Bank Deposit Box 		| **Strong**				        | **Strong** \[3]								|	**Durable**        		|
| Handwritten Paper Note  | Buried Somewhere 		| **Strong**				        | **Strong**										|	Fragile (Water)				|
| Stamped Metal Sheet [1]	| In Home 					  | **Strong**				        | Weak													|	**Durable**        		|
| Stamped Metal Sheet	    | Bank Deposit Box 		| **Strong**				        | **Strong** \[3]								|	**Durable**        		|
| Stamped Metal Sheet	    | Buried Somewhere 		| **Strong**				        | **Strong**										|	**Durable**        		|
| USB (Plaintext)					| In Home 						| **Strong**				        | Weak													|	Fragile (Water/Time)	|
| Memorised	[2]						| Brain								| **Strong**				        | **Strong**										|	Fragile (Time/Injury)	|

*\[1] There are many ways to do this, some are better than others - see Lopp's [initial comparison](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-21f47cf8e6f5) & more recent comparison: [Medium](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-part-ii-d309e04aefeb) / [Youtube](https://youtu.be/zFN__b6ARH4?t=20593)*

*\[2] Often referred  to as a [Brain Wallet](https://en.bitcoin.it/wiki/Brainwallet) - Not to be confused with a wallet where you generate the mnemonic using your brain (i.e. sentence from a book) a Brain Wallet is a wallet with a memorised mnemonic which was generated securely using a source of entropy.*

*\[3] Though likely far safer than your home there have been [reports](https://www.nbclosangeles.com/investigations/Safe-Deposit-Box-Theft-Missing-Items-Wells-Fargo-Bank-564733791.html) of theft of valuables from bank deposit boxes. That said, it is possible to store your seed in a nondescript manner, for example if on paper it could be written on the pages of a book. Provided there is some level of subtlety (don't write BITCOIN SEED at the top of the backup) I imagine a safety deposit box is quite safe from physical theft.*


There are three methods that are both Resistant to Theft and Durable;
- Handwritten Paper Note in a Bank Deposit Box
- Stamped Metal Sheet in a Bank Deposit Box
- Stamped Metal Sheet Buried Somewhere

A Bank Deposit Box is fine, but as discussed in the footnote above it requires some degree of trust in the bank.
Burying is fine, but it requires some degree of luck that someone won't find it / that you will be able to find it.

In either case, theft of the mnemonic seed can occur. Theft of an unencrypted seed is bad for two reasons;
A) The thief can spend your coins at any time. If they replace the seed there is no way for you to know that the seed is compromised.
B) You have lost your backup. You are unable to restore your seed, thus your bitcoin is lost whether or not the thief sweeps the funds.

You can use a watch only wallet to monitor the balance of your addresses, though if you see your funds move it is too late to do anything about it. Furthermore, if someone finds your watch only wallet they know how much bitcoin you have.

If you notice that your seed has been stolen you want to be able to quickly move your funds in-case the thief hasn't figured out what they stole, or they simply haven't swept the funds yet. For this reason is obvious that you should have MULTIPLE seed backups.

But with an **unencrypted seed**, each additional backup is an additional risk, because theft of any one of your backups is enough for a thief to steal your bitcoin. It would be better if you encrypted your seed, so that the thief wouldn't be able to steal your funds if they only have your 12/24 word mnemonic.

### Can I 'encrypt' my seed so that all is not lost if someone finds my mnemonic?

Yes, you can encrypt your seed by one of two methods:

#### 1) Use a passphrase alongside your mnemonic seed following [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki#from-mnemonic-to-seed)

Behind the scenes, many wallets use BIP39 encoding. All seeds encoded using BIP39 actually consist of the mnemonic + a passphrase.

If you didn't set a passphrase when making the wallet then is is empty / null / 1 /  ```""```.

Some wallets (e.g Samourai Wallet / ColdCard) will give you the option to set a custom passphrase (not to be confused with a password). The passphrase is sometimes referred to as a "seed extension", "extension word" or "the 13th/25th word".

##### Why use a passphrase?

Passphrases add flexibility and deniability at little cost provided you are aware that you are using a passphrase and the understand the implications of losing / forgetting it.

###### 1) Using a passphrase helps manage multiple isolated wallets.

You can use any passphrase in combination with your mnemonic seed to generate a 'valid' bitcoin wallet. This means that you can easily have a number of bitcoin wallets which all use the same mnemonic seed words but which have unique passphrases. Importantly each wallet will be completely independent.

For example suppose that you are a person with who publicly uses bitcoin and you also have an online identity because you were told never to use your real name online when you were a child and took it to heart.
You may want to have two wallets; One for bitcoin transactions relating to your public identity and the second relating to your online identity.

To do this you could have one wallet with passphrase ```"public-identity"``` and another with passphrase ```"online-identity"```. Both would use the same seed words so you only need to worry about (and go through the process of securely backing up) one mnemonic seed.

Now *if* someone finds your mnemonic seed they could attempt to "brute force" your passphrases (essentially trying to guess your passphrase by an automated process of trial and error), and this could lead them to discover the link between your identities (or they could accidentally reveal the link on-chain by making a transaction which spends from coins controlled by both wallets) so if its paramount that these identities never collide you should use completely independent seeds **which are stored in separate locations**.

###### 2) Using a passphrase can enable a duress wallet.
You could store some of your bitcoin using a null passphrase and most of your bitcoin in a wallet which uses a passphrase. A thief / attacker who obtains your seed words will take your bitcoin and be unaware that you have access to additional funds using your passphrase.

You can even make a wallet using a passphrase which you intend to give out to attackers in the case of duress (i.e. kidnapping). You could pre-fund this with some bitcoin so that if the attacker demands you give a passphrase you can do so.


###### 3) Light defence against a non-technical thief

If you **don't** use a passphrase and someone finds your bitcoin mnemonic seed then you will lose your bitcoin if this person enters your seed into a wallet and sends the bitcoin to an address that they control.

The thief need not be technically savvy or even understand bitcoin - they just need to realise that they have found a seed, perform an internet search and find a wallet that will let them import the seed words.

If you **do** use a passphrase and someone comes upon your bitcoin mnemonic seed they may give up after attempting to sweep the funds and finding no bitcoin (the seed without the passphrase will generate valid bitcoin addresses which will all be empty).

##### Other things to consider about passphrases

###### Backing Up:
Forget a weak passphrase and you will have to brute force it. Forget a strong passphrase (to protect against a thief brute forcing it) and you will lose your bitcoin forever.

There are many options with regard to backing up seeds, and adding passphrases into the mix complicates things further. The key is to consider the benefits of each option;

- **One location:** You can backup all your passphrases in the same location(s) as your mnemonic seed backup (s). No more risky than using a null passphrase but lets you manage multiple isolated wallets.

- **Twos separate locations:** You can backup all your passphrases in one location different to your mnemonic seed backup(s). Strictly more secure against physical theft than using a null passphrase (thief has to compromise multiple locations) and can mislead a thief into thinking that they have stolen your main bitcoin stash. Increases risk of losing access to your own bitcoin (if you lose all backups of passphrase you lose your bitcoin - risk not present when using a null passphrase).


- **X Separate Locations:** You can backup each passphrase in a separate location to your mnemonic seed. Some of the benefits from the above with some of the downsides. Requires more locations for backups for the same per wallet redundancy (though could plausibly hide multiple different passphrase backups in one location).

- **Combo:** You can store one or more passphrases with your mnemonic seed and one or more in separate locations. Again, some benefits of above options with some of the downsides. Probably quite good for deniability / duress situations where attacker is familiar with passphrases.

###### Long term viability:
Assuming you are using a bip39 encoded wallet using a passphrase introduces no more technical complexity than not using one because all bip39 wallets are encoded to use a null passphrase.

The spec (bip39) is widespread and well documented - In my opinion it's unlikely it will be lost to the relics of time. You can always store a copy of the bip39 readme and a software implementation if you are worried about this.

###### Risk of bitcoin loss:

If you use a passphrase and then forget it you will lose your bitcoin.

#### 2) Encrypt the plaintext seed words

You can take your mnemonic seed and use any encryption method to ensure that you need to use a password to decrypt the file.
You use either Physical or Digital Encryption Tools;

- **Physical Encryption Tool** ([e.g. Enigma](https://en.wikipedia.org/wiki/Enigma_machine) / [One Time Pad](https://en.wikipedia.org/wiki/One-time_pad)): Clearly if you are using a physical encryption tool you will need to ensure that the tool is commonly available so that you can decode when required. Enigma Machines are hard to come by - so they are not a practical solution. The One Time Pad provides perfect encryption, but remember - anyone with physical access to the pad can decode the mnemonic.
- **Digital Encryption Tool** ([e.g. VeraCrypt](https://www.veracrypt.fr/en/Home.html)): If you are using a digital encryption tool you will need to ensure that the computer on which you are encrypting/decrypting data is secure. The easiest way to do this is to use a temporary OS like [tails](https://tails.boum.org) on an old computer which is not connected to the Internet.

### Should I split my mnemonic in two (short version)?

This reduces the cryptographic security of your backup (it is far easier to brute force the private key with half the mnemonic words already known than with none known).

That said, the thief would have to know what the words are and either spend time cracking the seed themselves or sell the words to someone who would have no way to know the bitcoin they could steal before cracking the seed (so may be unwilling to pay for the first/last words).

If you are going to do this be sure to use a 24 word mnemonic seed (not a 12 word mnemonic seed).

It is better to use [Shamir's secret sharing](https://en.wikipedia.org/wiki/Shamir%27s_Secret_Sharing) to split the seed into 2 secrets, this way each piece of information is useless in isolation, and it is impossible to brute force the private key. The secrets can be recombined to recover the seed. You can also add redundancy, requiring say 2 of 3 of the secrets, or 3 of 5 (or any N of M). TailsOS comes with a pre-installed commandline tool called [ssss](http://point-at-infinity.org/ssss/) for this purpose.

[SLIP-0039](https://github.com/satoshilabs/slips/blob/master/slip-0039.md) will greatly increase the usage of sss.

Please let me know ([@6102bitcoin](https://keybase.io/6102)) if you can recommend any others.

### Should I split my mnemonic in two (long version)?

If an attacker knows the first/last 12 words of a 24 word seed the security against a brute force attack is greatly reduced (compared to brute forcing with none of the words known). Importantly it is more than twice as easy to brute force the half known seed (to understand without going into too much detail consider that 2^24 is 4096 times greater than 2^12).

All else being equal you should make it impossible for an attacker to access to any of your seed words.

In reality, all else is often not equal. It is important to consider the relative security of the options available to an individual when discussing bitcoin seed security.

Take Alice & Bob;
- Alice stores a full copy of her seed (24 words) in location A and a second full copy of her seed (24 words) in location B.
- Bob stores half his seed (12 words) in location A and the other half (12 words) in location B.

If an attacker (Charlie) goes to location A he can easily steal Alice's bitcoin with minimal effort or technical expertise - he simply has to identify that what he has found is a bitcoin seed and use a tool to try different derivation paths for the seed until he finds bitcoin to steal.

For Charlie to steal bob's bitcoin he will have to identify that he has found half a bitcoin wallet and then brute force the remaining 12 words. It is likely that this is computationally infeasible (more detailed analysis needed to verify this). It is also possible that the attacked would not be technically competent enough to brute force the seed, or that he wouldn't even realise that he has 12 words of a 24 word seed (perhaps he would assume that it's an invalid 12 word seed).

It would be natural to conclude that Bob's bitcoin seed is more secure than Alice's.

But now consider what would happen if Charlie is an arsonist (not a thief) and he sets location A on fire.

Regardless of how Alice stored her seed (on paper, stamped on metal etc.) she has a full backup in location B - she does not lose her bitcoin.
For Bob, how he stored his seed is now essential. He has no full backups, no redundancy. If the seed in location A is lost then so are all his bitcoin. Even if he stamped his seed into a metal plate it is possible that location A is an old building which collapsed in the fire, and his metal plate is buried under tonnes of brick and iron.

It would be natural to conclude that Alice's bitcoin are more secure then Bob's.

This example was simply meant to highlight that it is easy to forget that there are often trade-offs when it comes to securing your bitcoin seed. Though you should take care to minimize the risks posed by a sophisticated attacker capable of brute forcing half a 24 word seed you should first limit your exposure to risks which are more likely to pose a realistic threat (such as fire / malware / social attacks).

### Should I split my seed ABC into AB|BC|CA?

People will suggest using 3 partial seeds to a 24 word mnemonic seed, each with 16 words i.e. [1-16] , [9-24] , [17-24 & 1-8]. This does give some redundancy, but as discussed previously the relationship between number of revealed seed words and security against brute force attack is not linear.

As a simple exercise to compare of relative strength of 24, 12 and 8 unknown bits (0/1) compare the number of combinations possible. 2^24 = 16777216, 2^12 = 4096, 2^8 = 256.

There are ~ 4000 times fewer combinations of 12 bits than there are 24 bits, and ~65000 times fewer combinations of 8 bits than 24 bits. Other people will be able to crunch the actual numbers for BIP38 seeds, and it may be that the security of this method is still sufficiently high that it is a reasonable approach for almost everyone (excluding those which huge bitcoin holdings).   

This method (splitting seed into three 2/3 pieces) is simple, and does not require evaluation of any additional code (as is required for Shamir's Secret Sharing) but it does significantly lower the security against brute force attacks.

# 4) Using your seed

### Can I recover my bitcoin without my seed?
No. It is not possible to recover your bitcoin unless you have your seed. **Lose your seed, Lose your bitcoin**.

### Can I recover my bitcoin without my passphrase?
If you used a strong passphrase is not possible to recover your bitcoin (you need BOTH your mnemonic seed AND your passphrase). If you used a weak passphrase (or can't remember whether your passphrase was strong) you will have to try and brute force it. If anyone has opensource tools to do this please [get in touch](https://keybase.io/6102).

### I have forgotten my passphrase, what now?
If you still have access to your wallet (say you are using Samourai Wallet on your mobile and you can get into an existing wallet with your PIN code) you should consider IMMEDIATELY sending your bitcoin to a new wallet for which you have backups of both the Mnemonic Seed AND the passphrase.
Be aware that you damage your privacy by consolidating UTXO's. It may be prudent to;
- Mark all UTXO's as 'do not spend' excluding one UTXO
- Send your max balance to a new address generated using your new wallet (with a new, backed up Mnemonic seed & Passphrase).
- Once sent, unmark another UTXO
- Send that to a second, new address generated using your new wallet
- Repeat

### How should I recover bitcoin using my seed?

You should follow the same rules when recovering bitcoin using your seed as when you are generating your seed;
- Carefully control the environment in which the seed is exposed. The easiest way for non-technical people to do this is to buy a 'Hardware Wallet'. These devices store all the 'secret information' required to access your bitcoin on the dedicated hardware device so that it doesn't matter if your computer has viruses/malware. That said, some hardware wallets are better than others so make sure that you never enter your seed into your computer - only enter it into the device itself.

Remember that if anyone sees your seed it is potentially compromised, and should be treated as such.
For this reason make sure that you recover bitcoin from your seed somewhere that is private and that has no cameras/CCTV.
- Don't read your seed aloud as someone could hear it.
- Don't type it into a computer

### What is the Derivation Path?

See [walletsrecovery.org](https://walletsrecovery.org/) for detailed information about the derivation path for each wallet.

Also see [StackExchange](https://bitcoin.stackexchange.com/questions/78993/default-derivation-paths) for some more info.

### How often should I check backups?

You should definitely check your backup as part of your process for backing up. Provided that you have done this correctly there should be no need to actually sweep bitcoin from the backup unless you need the bitcoin. It is worth checking that the backup remains accessible at irregular intervals (say every 1-3 years). It is worth checking because if a single backup disappears you can recover using a secondary backup (if there is a chance that the backup was stolen) or make a replacement backup (if you are completely confident that the backup was just damaged, e.g. house fire). Don't regularly check backups (e.g. the 1st Jan each year) as this could be obvious and lead to people discovering your backup.

More reading on this subject: [SmartCustodyWhitePapers](https://github.com/BlockchainCommons/SmartCustodyWhitePapers/blob/master/%23SmartCustody-_Simple_Self-Custody_Cold_Storage_Scenario.md)

---
title: "Not Your Keys"
---

## ⚠️ DANGER ⚠️ - Not Your Keys, Not Your Coins

Owning bitcoin is knowing a private key which can be used to spend a bitcoin UTXO.

If any other person knows this private key, they could spend the UTXO.

For this reason, you must keep your private keys secure, and secret.

## Scams & Frauds

Scammers have been attempting to take bitcoin from uneducated users for years. One way to do this is to give an uneducated user a bitcoin wallet for which the scammer knows the private key.

The scammer can simply sit back and wait for the uneducated user to send bitcoin to this wallet, and at any time they can send all the bitcoin to their own address. The most malicious scammers may wait months or years before stealing the bitcoin, ensuring they steal as much as possible.

## Ballet

Recently a kickstarter campaign has gone live for 'ballet', a product which purports to be a simple and secure way to hold bitcoin without any setup. This product is shipped with the private key & an address physically printed/engraved on the product.

Specifically there are 3 elements to the design;
1. An encrypted private key printed on a sticker.
2. A 'wallet passphrase' engraved on the product with a scratch-off sticker covering it.
3. A public address printed on a sticker, stuck on top of the encrypted private key.

Anyone who can combine (1) & (2) can spend bitcoin sent to the address (3), be this person the owner of the product, the CEO of the company making this product, a malicious employee or an outside attacker.

## Don't Trust - Verify

The claim made by the manufacturer is that that (1) & (2) are not permanently recorded by the company, and thus the company can't steal your bitcoin.

**This is not a claim that you can verify.**

It is not possible for you, the user, to watch every step of every process for every device and inspect the code running on every machine and thoroughly check every room for hidden cameras.

It is not possible for anyone to do this, because it would require complete constant pervasive surveillance.

Even if the company is not intentionally planning to steal from those buying these products, they cannot guarantee that a malicious employee or an outside attacker has not compromised their process.

The product is sold under the false pretense that securing your bitcoin is a technologically challenging process which requires technical expertise and identity checks. This is NOT TRUE.

## The Solution

There are many [bitcoin wallets](https://bitcoin-only.com/#wallets) which can be checked against malicious injection of code designed to steal your bitcoin. Software releases are done in such a way that you can download a specific version of a tool and check that the hash of the file matches that which you have confirmed to be secure. Because many of the wallets listed are used by thousands of users & developers there are lot's of 'eyes on the code', that is to say that many people are watching the code changes to ensure that there is no funny business.

It is true that some users blindly download bitcoin wallets, these users are exposed to the aforementioned risk of using a wallet which has an insecure private key. However it is possible for users to check a version of a piece of software, to combine their efforts and verify that a certain version of software is secure. To track the changes made to the software over time to give reassurances that the code is secure for their use.

For this reason it is inaccurate to liken the risk of 'ballet' being insecure with the risk of a software wallet being secure. The former can NEVER be provably secure, whilst the latter can.

Furthermore, there are [actual bitcoin hardware wallets](https://bitcoin-hardware-wallet.github.io/) which are designed to allow you, the user, to generate, secure and backup your bitcoin private keys in such a way that you don't need to trust the wallet manufacturer (my favorite is the [ColdCard](https://coldcardwallet.com/)).

```
Archive of Text from ballet WEBSITE

1. Using an offline computer, serial number, wallet passphrase, and intermediate code are generated in Ballet’s USA headquarters
2. Serial number and intermediate code are then electronically transmitted to Ballet’s office in China.
3. Afterwards, the BIP38 process is used to randomly generate an encrypted private key (EPK) using the intermediate code data.

The corresponding public key and coin addresses will be generated, along with a confirmation code, to be used for verification and additional checking afterwards.
This encrypted private key is secure data, which is only stored once, on a hard disk drive.

In China, this two-layer QR code sticker is manufactured using an offline process in a secure printing facility

The secure data is never transmitted to any external computers or system.
The secure data is transferred physically, on a hard disk drive.
Right after the printing process, the secure data is then deleted, overwritten, and physically destroyed.

The secure two-layer QR code sticker will then be securely applied to the hardware wallets, without ever revealing the encrypted private keys.

Once finished, the partially assembled wallets are sent to the United States for final production.
The confirmation codes are also electronically sent back to the United States.
This is for further verification to ensure that the encrypted private keys and decryption wallet passphrase does match up with the generated cryptocurrency coin addresses.

The hardware wallets and QR code stickers are verified and double checked in the United States according to their corresponding serial numbers.

The matching decryption wallet passphrase and serial number will then be laser etched onto the wallets.
A strip of tamper evident scratch-off material is then applied on the wallet, to cover the wallet passphrase.
```

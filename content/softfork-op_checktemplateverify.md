---
title: "Schnorr / Taproot"
---

| [--- Softfork Overview ---](/softfork-overview) |
|:-:|

## BIP Numbers:
- [BIP 340](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki): Schnorr Signatures for secp256k1
- [BIP 341](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki): Taproot: SegWit version 1 output spending rules
- [BIP 342](https://github.com/bitcoin/bips/blob/master/bip-0342.mediawiki): Tapscript: Validation of Taproot Scripts

----

## BIP 340
This is a new standard and is not part of any softfork.

This BIP simply defines a standard which uses a better signature scheme (Schnorr) in place of the scheme currently used (ECDAS: secp256k1).

Advantages of Schnorr are that it is Provably secure, Non-malleable and Linear.

The linearity is a key benefit, multisig transactions will appear the same as single sig transactions.

> "If there are no disadvantages why doesn't bitcoin already use Schnorr?"

When bitcoin was released the schnorr patent was just expired / expiring and satoshi chose to use ECDSA instead as it was more widespread and included in software libraries.

[Read More ...](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki)

----

## BIP 341
This is a new rule which requires a softfork to activate.

The high level aim is to reduce the amount of information revealed about the conditions for spending a UTXO, improving privacy.

[Read More ...](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki)

----

## BIP 342
This is a new rule which requires a softfork to activate.

The high level aim is to improve bitcoin's script structure by;
- Adding 1 new OPCODE: `OP_CHECKSIGADD`
- Modifying 2 OPCODES: `OP_CHECKSIG` & `OP_CHECKSIGVERIFY`
- Disabling 2 OPCODES: `OP_CHECKMULTISIG` & `OP_CHECKMULTISIGVERIFY`

It is backwards compatible in that a node running pre-softfork rules will mark a taproot transaction as valid (Using `OP_SUCCESSx`)

It is intended to be added in tandem with BIP341.

[Read More ...](https://github.com/bitcoin/bips/blob/master/bip-0342.mediawiki)

----
# Videos
| Title                             | Author              |
| -----                             | ------              |
| [Taproot, and Schnorr, and SIGHASH_NOINPUT, oh my!](https://www.youtube.com/watch?v=YSUVRj8iznU&feature=youtu.be) | Pieter Wuille |

# Written Analysis
| Title                             | Author              |
| -----                             | ------              |
| [The Schnorr Signature & Taproot Softfork Proposal](https://blog.bitmex.com/the-schnorr-signature-taproot-softfork-proposal/) | Bitmex Research |
| [Taproot Is Coming: What It Is, and How It Will Benefit Bitcoin](https://bitcoinmagazine.com/articles/taproot-coming-what-it-and-how-it-will-benefit-bitcoin) | Aaron van Wirdum |

# Spoken Analysis
| Title                             | Author  |
| -----                             | ------- |
| [TFTC #131](https://talesfromthecrypt.libsyn.com/tales-from-the-crypt-131-matt-corallo-valentine-wallace) | Marty Bent, Matt Odell, Matt Corallo, Val Wallace|

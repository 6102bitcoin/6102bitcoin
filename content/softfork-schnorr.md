---
title: "Schnorr"
---

| [--- Softfork Overview ---](/softfork-overview) |
|:-:|

## BIP Numbers:
- [BIP 340](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki): Schnorr Signatures for secp256k1

+ See [Taproot](/softfork-taproot) & [Tapscript](/softfork-tapscript)
----

## BIP 340
This is a new standard and is part of the taproot softfork.

This BIP simply defines a standard which uses a better signature scheme (Schnorr) in place of the scheme currently used (ECDAS: secp256k1).

Advantages of Schnorr are that it is Provably secure, Non-malleable and Linear.

The linearity is a key benefit, multisig transactions will appear the same as single sig transactions.

> "If there are no disadvantages why doesn't bitcoin already use Schnorr?"

When bitcoin was released the schnorr patent was just expired / expiring and satoshi chose to use ECDSA instead as it was more widespread and included in software libraries.

[Read More ...](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki)

----

# Videos
| Title                             | Author              |
| -----                             | ------              |
| [Taproot, and Schnorr, and SIGHASH_NOINPUT, oh my!](https://www.youtube.com/watch?v=YSUVRj8iznU&feature=youtu.be) | Pieter Wuille |
| [BIP340 Read Through](https://www.youtube.com/watch?v=rVsNFMzQUck&feature=emb_logo) | Jimmy Song |

# Written Analysis
| Title                             | Author              |
| -----                             | ------              |
| [Visual Overview of Schnorr Signatures for Bitcoin](https://veriphi.io/en/blog/visual-overview-of-schnorr-signatures-for-bitcoin) | Veriphi |
| [The Schnorr Signature & Taproot Softfork Proposal](https://blog.bitmex.com/the-schnorr-signature-taproot-softfork-proposal/) | Bitmex Research |
| [Taproot Is Coming: What It Is, and How It Will Benefit Bitcoin](https://bitcoinmagazine.com/articles/taproot-coming-what-it-and-how-it-will-benefit-bitcoin) | Aaron van Wirdum |

# Spoken Analysis
| Title                             | Author  |
| -----                             | ------- |
| [TFTC #131](https://talesfromthecrypt.libsyn.com/tales-from-the-crypt-131-matt-corallo-valentine-wallace) | Marty Bent, Matt Odell, Matt Corallo, Val Wallace|
| [SLP137](https://stephanlivera.com/episode/137/) | Stephan Livera & AJ Towns |

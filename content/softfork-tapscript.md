---
title: "Tapscript"
---

| [--- Softfork Overview ---](/softfork-overview) |
|:-:|

## BIP Numbers:
- [BIP 342](https://github.com/bitcoin/bips/blob/master/bip-0342.mediawiki): Tapscript: Validation of Taproot Scripts

+ See [Schnorr](/softfork-tapscript) & [Taproot](/softfork-tapscript)

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
| [BIP340 Read Through](https://www.youtube.com/watch?v=rVsNFMzQUck&feature=emb_logo) | Jimmy Song |

# Written Analysis
| Title                             | Author              |
| -----                             | ------              |
| [The Schnorr Signature & Taproot Softfork Proposal](https://blog.bitmex.com/the-schnorr-signature-taproot-softfork-proposal/) | Bitmex Research |
| [Taproot Is Coming: What It Is, and How It Will Benefit Bitcoin](https://bitcoinmagazine.com/articles/taproot-coming-what-it-and-how-it-will-benefit-bitcoin) | Aaron van Wirdum |

# Spoken Analysis
| Title                             | Author  |
| -----                             | ------- |
| [TFTC #131](https://talesfromthecrypt.libsyn.com/tales-from-the-crypt-131-matt-corallo-valentine-wallace) | Marty Bent, Matt Odell, Matt Corallo, Val Wallace|
| [SLP137](https://stephanlivera.com/episode/137/) | Stephan Livera & AJ Towns |

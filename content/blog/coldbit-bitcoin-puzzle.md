---
title: "Coldbit Bitcoin Puzzle"
---

Coldbit made a bitcoin puzzle which I was fortunate enough to solve first - netting me 1 000 000 sats (or 0.01 BTC). 
I include details of how I mixed this prize with whirlpool so that you can't follow my coins!

This is the announcement made on twitter:

{{< figure src="/img/coldbit-bitcoin-puzzle-tweet.png" alt="" position="center" style="border-radius: 8px;" caption="Puzzle announcement" captionPosition="centre" captionStyle="color: grey;" >}}

Here is a high resolution copy of the image in the tweet:

{{< figure src="/img/coldbit-bitcoin-puzzle.jpeg" alt="" position="center" style="border-radius: 8px;" caption="Image provided as part of Puzzle announcement" captionPosition="centre" captionStyle="color: grey;" >}}

It shows three metal bitcoin seed backups (made by Coldbit) with engraved artwork.

A number of other clues were given in the thread. Most importantly, [the address we are looking for](https://twitter.com/ColdbitWallet/status/1318216798928592896): `1Q7QWSMhQWdJ46o6MRPdtr7FLaDbwpaShq` 

# The Proper Solution

_Note: In hindsight this is how you should have solved the problem. See my notes at the bottom for what I actually did_

Coldbit sell the three products (which are shown in the image) on their [store page](https://coldbit.com/product-category/coldbit-steel/).

{{< figure src="/img/coldbit-store.png" alt="" position="center" style="border-radius: 8px;" caption="Coldbit store" captionPosition="centre" captionStyle="color: grey;" >}}

- The leftmost puzzle image is a product named `Cortez`
- The centre puzzle image is a product named `Shodan`
- The rightmost puzzle image is a product named `Bionic`

Reading left to right we have `Cortez Shodan Bionic`

`sha256(Cortez Shodan Bionic)` = `47b2e9f37b6d3d6e03b04737ef95484d0a4cdf9b5234e2e0bbd204a42ecb09f4`

Next:
- Clone this useful [bash tool](https://github.com/grondilu/bitcoin-bash-tools/), - run `./bitcoin.sh` 
- type `newBitcoinKey 0x47b2e9f37b6d3d6e03b04737ef95484d0a4cdf9b5234e2e0bbd204a42ecb09f4` (the sha256sum with an 0x prefix)

The output is 

```
---
secret exponent:          0x47B2E9F37B6D3D6E03B04737EF95484D0A4CDF9B5234E2E0BBD204A42ECB09F4
public key:
    X:                    CFDE434849B96F9EEAD8D1E5202814591AC1F9F1E030C1157286CAD325E5209E
    Y:                    F1470FAAB16361093A14F8C7FEC2FA3C272ABCC327920C390B6665F3F11A0264
compressed:
    WIF:                  Kyd5qJEvpYXtSKWuXNERx3g7NRCax65sY125v1k1U8jUhxeEAkmW
    bitcoin address:      1Q7QWSMhQWdJ46o6MRPdtr7FLaDbwpaShq
uncompressed:
    WIF:                  5JMs2t2oBKUPXfBQEDy4PSXcRnp2oTyqc7oTwc4QDVVCiWmmK6o
    bitcoin address:      18DdegWruB2NW9oyPApYLmhzrQdonVLmy5
```

The compressed address matches the address given previously by coldbit.

All that is left is to enter the `wif` (`Kyd5qJEvpYXtSKWuXNERx3g7NRCax65sY125v1k1U8jUhxeEAkmW`) into a wallet to sweep the coins and then send them to an address we control.

In this case I sent the utxo to `bc1qp0w2ej7y3mcl8fvjnpe6grqnes0sfw76qwr6rf` in [this transaction](https://mempool.space/address/bc1qp0w2ej7y3mcl8fvjnpe6grqnes0sfw76qwr6rf) leaving 8640 sats as a miner fee. 
This is 45.7 sat/vB which was sufficient to get into the next block. 

# Goodbye Privacy?

The issue now is that everyone knows that I am in control of this bitcoin address.
If I were to spend this on a product, the merchant could link the transaction to me (6102). 

We need a way to resolve this issue, so that I can spend the bitcoin without any privacy concerns.

My chosen solution is to mix with whirlpool (a CoinJoin implementation).

# Whirlpool

Anticipating this step I actually swept the prize UTXO to my samourai wallet which is connected (over tor) to my Ronin Dojo node. 

I already have whirlpool set up so I start by going to the `whirlpool` section of the wallet and pressing the `mix utxos` button.

Next I need to select the utxos to be mixed. 

I spent `8640 sats` moving the bitcoin to an address which I control, therefore I now have a `0.00991360 BTC` utxo. 

The minimum amount you can mix is the smallest pool size (currently 0.01 BTC), therefore this utxo is too small to be mixed alone.

As such, I must select another utxo to be merged - this is where address labels are essential.

Address labels are short notes which provide information about a utxo. 

I label my addresses in Samourai Wallet - so it is easy for me to identify a utxo which can be merged without any privacy issues.

I select an appropriate utxo and select the 0.01 BTC pool.

_Note: In whirlpool the fee you pay to the developers is a fixed amount for each pool. For this reason, you typically mix an amount somewhat larger than the pool in order to economise (mixing 0.1 BTC costs the same as mixing 0.01 BTC). In this case I just want to mix these two utxos, so I proceed with this mix._

The wallet creates a `TxO` transaction. 

{{< figure src="/img/example-tx0.png" alt="" position="center" style="border-radius: 8px;" caption="Tx0 - [txid:a0aa9af2a6e5e8c775aeaeaf3523e6621f6018dff6307d6c19019283a6751ce2](https://mempool.space/tx/a0aa9af2a6e5e8c775aeaeaf3523e6621f6018dff6307d6c19019283a6751ce2" captionPosition="centre" captionStyle="color: grey;" >}}

This transaction contains:
- Both the selected utxos as inputs (`bc1qrv...s4j` & `bc1qp0...6rf`) 
- An Op_Return: `VlÙòéÉùZ£¸Æ¨ÃµËÙC+Z8àúë=µËÞéí+;Æ>È9òYÒCÆ¥?b(X?x}qUV`	
- An output which is equal to the pool size + a transaction fee (`bc1qfu...an8	0.01009500 BTC`)
- An output which pays the whirlpool coordinator (`bc1quqn...ueu	0.00050000 BTC`)
- A change output (`bc1q75...xvk	0.00053177 BTC`)

It is important to note that:
- The inputs can now be grouped with the common input ownership heuristic. In the future multiparty Tx0 transactions will be possible which will undermine this heuristic.
- The change output is deterministically linked to both the inputs. This means it is critical that I don't accidentally include this in another transaction. Samourai Wallet automatically marks this address as `Do Not Spend` to ensure that this doesn't happen & also tags it with a `tx0 change` label.

I set a similar fee for the tx0 as I had done in the previous transaction, however this time the transaction took ~ 1h to confirm. 

Once the tx0 transaction had confirmed, the [mix transaction](https://mempool.space/tx/e14ed3bf4e5db2eeee5eaff39a2fad4a23cd09aed3456c042d8ad38526a9f4ff) was broadcast almost instantly.

{{< figure src="/img/whirlpool-mix.png" alt="" position="center" style="border-radius: 8px;" caption="Whirlpool Mix Transaction. " captionPosition="centre" captionStyle="color: grey;" >}}

As you can see, there are 5 inputs and 5 outputs. 

Inputs
- Three of the inputs have a value of exactly `0.01 BTC` 
- My input (with a value of `0.01009500 BTC`).
- One other new input with a value of `0.01008167 BTC` 

Outputs
- Five identical outputs, each with a value of exactly `0.01 BTC`

Things to note:
- The three equal value (`0.01 BTC`) inputs are 'freerider' utxos i.e. Remixers. They pay no additional coordinator or transaction fee and are randomly selected from the pool of mixed utxos from all users who are running whirlpool.
- My input and the other input pay the transaction fee.
- Because all the outputs are identical, any of them could be interpreted as my transaction. There are zero deterministic links between my input and the output that belongs to me.

# The cost of privacy

Fee Summary

| Description               | Amount (sats)         | % of Prize        |
| ---                       | ---                   | ---               |
| tx fee to sweep           |     8 640             |   0.864           |
| tx fee to tx0             |    14 440             |   1.440           |
| tx fee to mix             |     9 500             |   0.950           |
| Coordinator fee           |    50 000             |   5.000           |

If I had not been concerned about privacy I would have only paid the tx fee to sweep.

Total Fees (No privacy) = 0.840 %

Total Fees (Private)    = 8.254 %

As mentioned, mixing the amount I did was relatively expensive. If I had other utxo's which I could have safely merged I could have mixed 0.1 BTC in the 0.01 BTC pool and paid significantly lower % fee. 

# What I actually did

I was actually not at my computer when I solved this, so I used an online brainwallet website. I wouldn't use this for bitcoin I own, but as it wasn't my bitcoin at risk I figured it was better than nothing. I wasn't satisfied with this so after I got to my computer I ran through the steps above, which are more secure.

Also - I didn't immediately realise the names of the products were the key. I searched for `System Shock` and discovered a video game of the same name which had a cyberpunk asthetic. I found the image below when looking at images of the game, this is a character named `Shodan`.

{{< figure src="/img/coldbit-bitcoin-puzzle-shodan.jpg" alt="" position="center" style="border-radius: 8px;" caption="Shodan - A character from the System Shock Videogame" captionPosition="centre" captionStyle="color: grey;" >}}

It looked very similar to the centre puzzle image.
Next, I shared the image in a telegram chat and [REDACTED] pointed out that the name was the same as a product for sale on the coldbit website. 
Looking through the other products and realized that each product was named after a character from the game. 
At that point I knew that it would be come combination of the names, so tried them in order from left to right - Fortunately this was correct. 
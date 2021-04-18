---
title: "Compliant Miners"
---

I shall attempt to briefly explain why I think that the game theory of mining will result in regular non-compliant blocks being mined.

My hope is that this can put to rest the concerns that a minority compliant group of miners will force the network into a compliant system. 

If you believe that I have made an error please [get in touch](https://twitter.com/6102bitcoin) and explain where you think I went wrong.

# Terminology

| Block Type          | Definition                                                            |
| ---                 | ---                                                                   |
| Compliant `C`       | A block which **does not** contain any blacklisted transactions       |
| Non-Compliant `NC`  | A block which **does** contain blacklisted transactions               |

| Miner             | Definition                                                     |
| ---               | ---                                                            |
| Compliant `C`     | Only build on `C` blocks. Only produces `C` blocks |
| Rational          | Maximize expected return  | 

## The Setup:
Consider that there is a long chain of `C` blocks mined.

## The `NC` Block:
A miner produces a `NC` block for reasons that I will explain below.

## The Response
By definition the `C` miners ignore this block, and mine on the last `C` block. 
They continue working on a stale chain at elevated risk of producing a block that is not built upon.
In order to do this they must operate at a loss.

Mining on a stale chain with a minority hashrate is an easy way to go broke.

The rational miners have three options:
1. Mine a `C` block on the last `C` block
2. Mine a `C` block on the chaintip (a `NC` block)
3. Mine a `NC` block on the chaintip (a `NC` block)

Given the `C` miners have a minority hashrate the rational miners will not orphan the `NC` block. 
If they did, they would likely fall behind the chaintip as the majority of miners will be mining on a later block. 

That rules out option 1. 

Next the miner can decide whether to mine a `C` or a `NC` block.

The chance of the (minority hashpower) `C` miner catching up and then overtaking a 2 block lead is very small. This means that the orphan risk of producing a `NC` block and getting orphaned is very low, and the increased profit from mining `NC` transactions will likely outweigh the risks of mining a `NC` block.

But there is another key benefit from mining a `NC` block - the `C` miners will not be able to mine upon it, and therefore those miners will effectively not be mining.
As such, until the next difficulty adjustment the profitability of the miners mining on the `NC` chain will be greater in proportion to the fraction of the `C` hashpower.

## Who mines the first `NC` block?
I expect that in reality a small group of ideologically (not economically) driven miners would be willing to take the risk of having their block orphaned in order to create the first `NC` block (after which the rational miners are expected to extend the `NC` chain).

**However, this is not required for a `NC` block to be produced.**

If a user attempting to spend a blacklisted utxo finds their `NC` transaction stuck in the mempool despite a suitable fee they have 2 options. 
The first is to do nothing, and accept their their utxo is currently unspendable.
The second is to increase the fee to entice a miner to mine a `NC` block.

Though some individuals will be able to delay making a transaction with their blocked utxo, others will not have that luxury. 
Over time the transaction fees associated with `NC` transactions will increase.
For the users attempting to make these transactions the fee that they are willing to pay will grow to a large fraction of the transaction amount. 

Eventually expected loss due to the orphan risk (when mining a NC block) will be less than the fees on offer, at this point even a rational miner will choose to mine a `NC` block.


# What if Censors mine on any block

Then the risk of having a NC block orphaned is not even furtger reduced. 


---

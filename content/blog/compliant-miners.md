---
title: "Compliant Miners"
---

I shall attempt to briefly explain why I think that the game theory of mining will result in regular non-compliant blocks being mined.

My hope is that this can put to rest the concerns that a minority compliant group of miners will force the network into a compliant system. 

If you believe that I have made an error please [get in touch](https://twitter.com/6102bitcoin) and explain where you think I went wrong.

# Terminology

| Block Type          | Definition                                                            |
| ---                 | ---                                                                   |
| compliant (C)       | A block which **does not** contain any blacklisted transactions       |
| non-compliant (NC)  | A block which **does** contain blacklisted transactions               |

| Miner             | Definition                                                     |
| ---               | ---                                                            |
| compliant         | Only build on compliant blocks. Only produces compliant blocks |
| rational          | Maximize expected return  | 

## The Setup:
Consider that there is a long chain of compliant (C) blocks mined.

## The Non-Compliant Block:
A miner produces a non-compliant (NC) block for reasons that I will explain below.

## The Response
By definition the compliant miners ignore this block, and mine on the last compliant block. 
They continue working on a stale chain at elevated risk of producing a block that is not built upon.
In order to do this they must operate at a loss.

The rational miners have three options:
1. Mine a compliant block on the last compliant block
2. Mine a compliant block on the chaintip (a non-compliant block)
3. Mine a non-compliant block on the chaintip (a non-compliant block)

Given the compliant miners have a minority hashrate the rational miners will not orphan the non-compliant block. 
If they did, they would likely fall behind the chaintip as the majority of miners will be mining on a later block. 

That rules out option 1. 

Next the miner can decide whether to mine a compliant or a non-compliant block.

The chance of the (minority hashpower) compliant miner catching up and then overtaking a 2 block lead is very small. This means that the orphan risk of producing a non-compliant block and getting orphaned is very low, and the increased profit from mining non-compliant transactions will likely outweigh the risks of mining a non-compliant block.

But there is another key benefit from mining a non-compliant block - the compliant miners will not be able to mine upon it, and therefore those miners will effectively not be mining.
As such, until the next difficulty adjustment the profitability of the miners mining on the non-compliant chain will be greater in proportion to the fraction of the compliant hashpower.

## Who mines the first non-compliant block?
I expect that in reality a small group of ideologically (not economically) driven miners would be willing to take the risk of having their block orphaned in order to create the first non-compliant block (after which the rational miners are expected to extend the non-compliant chain).

**However, this is not required for a non-compliant block to be produced.**

If a user attempting to spend a blacklisted utxo finds their non-compliant transaction stuck in the mempool despite a suitable fee they have 2 options. 
The first is to do nothing, and accept their their utxo is currently unspendable.
The second is to increase the fee to entice a miner to mine a non-compliant block.

Though some individuals will be able to delay making a transaction with their blocked utxo, others will not have that luxury. 
Over time the transaction fees associated with non-compliant transactions will increase.
For the users attempting to make these transactions the fee that they are willing to pay will grow to a large fraction of the transaction amount. 

Eventually expected loss due to the orphan risk (when mining a NC block) will be less than the fees on offer, at this point even a rational miner will choose to mine a non-compliant block.

---
---
title: "Compliant Miners"
---


This is an initial reply to [this](https://juraj.bednar.io/en/blog-en/2020/11/18/bitcoin-censorship-will-most-likely-come-pt-2/) article by Juraj Bednar. 

# Terminology

| Block Type      | Definition                                                                |
| ---             | ---                                                                       |
| Compliant       | A block which **does not** contain any blacklisted transactions           |
| Non Compliant   | A block which **does** contain blacklisted transactions                   |

| Miner                 | Definition                                                                |
| ---                   | ---                                                                       |
| Compliant             | A miner which will build on any compliant block and only produces compliant blocks                      |
| Rational              | A miner which builds on whatever block allows them to produce a block with the highest expected return  |
| Cypherpunk            | A miner which builds a non compliant block on the chaintip                                              |  
| Bandwagon Rebel       | A miner which builds a non compliant block whenever the chaintip is a non compliant block               |  


Quoting the very start of the article ...

> I assume that there is a 10% (example) minority that is forced by a regulator (i.e. government has guns pointed at them) to do these two things:
> 1. Never mine a transaction spending a utxo (or alternatively an utxo belonging to an address) that is on a published blacklist, or any other transaction following from that (at that time spent) transaction output. This rules out any coinjoin that has a tainted input – all outputs are then tainted.
> 2. Never mine on top of one block that breaks the previous rule. This does not mean that a compliant miner should be stuck forever in a minority chain.

Point 1 is a dynamic blacklist that uses the ['poison' method](https://6102bitcoin.com/001_what_is_bitcoin_taint/) for taint tracking If at some distance from the original blacklisted utxo the taint is ignored, this is [trivial to overcome](https://6102bitcoin.com/003_blacklisting_distance_proximity/). If all linked utxos are tainted, this will lead to an ever increasing number of tainted utxos. 

Point 2 is suggesting that the compliant miner only cares about the block directly being build upon. Let us consider the various possible scenarios assuming that at block height X-2 a compliant block is mined....

Columns on the right show the the block number that each miner will mine upon, followed by the type of block (assuming a non compliant transaction is available), which is either compliant (C) or non compliant (NC)... let the rational miner's block type remain unspecified for now (?).

|               | Block X - 2   | Block X - 1       | Block X       | Compliant | Rational | Cypherpunk | Bandwagon Rebel   |        
| ---           | ---           | ---               | ---           | ---       | ---      | ---        | ---               |   
| Scenario 1    | Compliant     | Compliant         | Compliant     | X   / C   | X / ?    | X / NC     | X / C             |
| Scenario 2    | Compliant     | Non Compliant     | Compliant     | X   / C   | X / ?    | X / NC     | X / C             |
| Scenario 3    | Compliant     | Compliant         | Non Compliant | X-1 / C   | ? / ?    | X / NC     | X / NC            |
| Scenario 4    | Compliant     | Non Compliant     | Non Compliant | X-2 / C   | X / NC   | X / NC     | X / NC            |

## Scenario 1 

Everyone mines on the chaintip. In this scenario I concede that the rational miners decision is important. If they **always** choose to mine compliant blocks Scenario 1 will persist, unless a sufficient minority of cypherpunk miners exist to trigger a switch to scenario 4. **However**, in this scenario censored parties will increase their fees up until the fee is the **entire utxo value**. As such, in this scenario the incentive to mine a non compliant block will increase, and if sufficient fees are available to incentivize the rational miners to mine a non compliant block, scenario 3 is entered. 

## Scenario 2

Everyone mines on the chaintip. In this scenario I again concede that the rational miners decision is important. If they **always** choose to mine compliant blocks then the chance of moving from Scenario 2 -> 3 or 4 is lowered (but still not zero). However, again, the incentive to mine a non compliant block will grow over time, and if sufficient fees are available to incentivize the rational miners, scenario 3 is entered. 

## Scenario 3 

- The compliant miner rejects the chaintip and mines on block X-1 (the last compliant block). 
- The Bandwagon Rebels join the Cypherpunks in trying to mine a non compliant block, hoping to enter Scenario 4. 

If the rational miner mines a non compliant block, the scenario switches to Scenario 4, and it is exceedingly likely that the compliant chain dies, as all other parties will be mining on the chaintip while the compliant miner is 2 blocks behind. They keep the extra revenue from mining the censored transactions.

If the rational miner mines a compliant block, they forfeit the potential extra revenue.

## Scenario 4

- The compliant miner rejects the chaintip and mines on block X-2. They fall behind and likely never to catch up.
- The Bandwagon Rebels likely choose to continue mining non compliant blocks, stopping the compliant miners from returning to the network.
- The rational miners **mine non compliant blocks**, stopping the compliant miners from returning to the network, increasing their profits until the next difficulty adjustment.
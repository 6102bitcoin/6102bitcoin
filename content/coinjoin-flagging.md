---
title: "CoinJoin Flagging"
---

| See [CoinJoin Overview](/coinjoin-overview) & other CoinJoin work on the [project page](/projects)|
|-|

## Introduction

There is a huge effort underway to discourage bitcoiners from making CoinJoin transactions.

This is a coordinated effort which involves many large exchanges, analytics companies and no doubt sell out bitcoiners.

Don't be coerced into giving up your privacy.

{{< figure src="/img/SLP138-Matt-Odell.png" alt="" position="center" style="border-radius: 8px;" caption="Recommended Listening: [SLP138](https://stephanlivera.com/episode/138/)" captionPosition="centre" captionStyle="color: grey;" >}}

## CoinJoin

Bitcoin transactions are public. Used naïvely this makes bitcoin transactions very easy to follow, meaning that bitcoin is not private by default. Used carefully (with the correct tools) bitcoin can be used quite privately and much work is being done to improve both the ease of using bitcoin privately & the cutting edge of bitcoin privacy.

One key tool used by those looking to use bitcoin more privately is CoinJoin. I have written an [overview](/coinjoin-overview) for those who are unfamiliar, but put simply it is a process of mixing your coins with those of other strangers in such a way that it is not possible to determine with certainty the links between the bitcoin that goes into the CoinJoin transaction, and those which emerge from the other side.

## Fungibility Risk

A frequent concern of users learning to improve their bitcoin privacy is whether their bitcoin will be more difficult to sell / exchange after mixing. They wonder whether mixed ‘tainted’ coins are less valuable than ‘untainted’ coins, i.e. whether bitcoin is fungible.

## Taint

Typically people describe coins as either having no Taint (A freshly mined coin which has no ‘history’ to speak of) to being Tainted (A coin which for which the pubkey is widely known to be a scammer’s repeatedly re-used address.)

The ‘Tainted’ coin is only such because the address of the scammer is known to the analyst. Suppose that the analyst doesn’t know this vital piece of information, would the coin still be tainted? It should be clear that the degree to which coins can be classified as tainted depends on the level of information available to the person doing the classifying.

As such, taint is not an intrinsic property of the coin (unlike, for example, the value of the coin in satoshis), it is an extrinsic property imposed ON the coin BY the analyst.

## A growing trend.

Prior to late 2019 I am not aware of there having been any reported issues selling / exchanging bitcoins which have been mixed. Since late 2019 there have been a growing number of exchanges contacting users following their use of CoinJoin tools pre/post withdrawal.

## Possible Options for Users

1. CoinJoin & Opt-Out of Exchanges

This is the best option. Exchanges which require KYC documentation are security holes and have been hacked time and time again.
Vote with your feet and stop using exchanges which do this.
A number of non KYC Options exist (most notably BISQ which is a P2P exchange)

2. CoinJoin & Continue using Exchanges

This is an option which many will take due to the convenience of KYC exchanges (particularly if you have already been 'verified').
Users attempting this risk having their accounts locked for breaking (potentially unwritten) rules.
Typically users doing this attempt to put distance between the exchange and their mixed coins by sending through multiple intermediate addresses.

3. Stop CoinJoining

This is the worst option.
It's not normal for companies to undergo pervasive and indefinite surveillance on paying customers. **Push back.**

## Pay With CoinJoin

Regardless of your decision above, consider paying with mixed coins when spending your bitcoin.
If people pay with mixed coins for normal 'legitimate' goods and services the heuristic that mixed coins are suspicious is broken.
Even better, the merchant you shop at has coins 1 step removed from a CoinJoin tx, analytics companies / exchanges won't be able to ban these users who have no way to selectively accept payments.

## Are exchanges currently flagging users who CoinJoin their withdrawals?
It is unclear.

It might be that they are performing a proximity based analysis, in which case mixing with wasabi is a particular issue because the wasabi coordinator fee address is fixed making your inputs closely linked to known scammers via the wasabi coordinator address.

Wasabi has been used in the past to mix funds from the plustoken scam, UTXO's used as inputs in TX1:
- `Plustoken UTXO`
- `Wasabi Coordinator Addr`

Suppose I mix `my UTXO` with wasabi, UTXO's used as inputs in TX2:
- `Plustoken UTXO`
- `Wasabi Coordinator Addr`

As such, a proximity analysis may flag that `my UTXO` and `Plustoken UTXO` have close proximity.


## That said, they absolutely _could_ flag CoinJoins.

If they start doing this I recommend immediately withdrawing everything (if you haven't already) and using a different exchange.

If that's not an option you'll need to find out how many hops are required before they assume they are no longer your coins.

**Obviously it's better to leave now than wait to see whether this happens**

## Which companies flag users who CoinJoin?

Bitlicense Exchanges

| Exchange        | Issue Count   | Sources  |
| --------        | :---------:   | :-----:  |
| Circle          |               |          |
| Paxos           | 1             | [(1)](https://twitter.com/RonaldMcHodled/status/1222172084610027523)        |
| CoinBase        |               |          |
| BitFlyer        |               |          |
| Cash App (Square)|              |          |
| BitPay          |               |          |
| Coinsource      |               |          |
| Bitstamp        | 1             | (1**)     |
| Sofi            |               |          |
| Genesis Global  |               |          |
| RobinHood Crypto|               |          |

CIOS Exchanges:

| Exchange        | Issue Count   | Sources  |
| --------        | -----------   | -------  |
| Binance         | 1             | [(1)](https://twitter.com/bittlecat/status/1207621591820951552)         |
| Paxful          | 1             | [(1)](https://web.archive.org/web/20200128234015/https://old.reddit.com/r/WasabiWallet/comments/czext2/paxful_account_was_frozen_due_to_coinjoin/)         |
| Bitfinex        | 1             | [(1)](https://web.archive.org/web/20200128233910/https://old.reddit.com/r/WasabiWallet/comments/beqj8r/bitfinex_lock_account/)       |


Other Companies:

| Exchange        | Issue Count   | Sources  |
| --------        | -----------   | -------  |
| BlockFi         | 1             | [(1a)](https://twitter.com/matt_odell/status/1234514628115341313), [(1b)](https://tweetstamp.org/1234531935038341120)   |
| BitVavo         | 1             | [(1)](https://web.archive.org/web/20200907203529if_/https://www.reddit.com/r/Bitcoin/comments/i8ye6x/exchange_account_closed_because_of_risk_profile/) |
| BottlePay       | 2             | [(1)](https://twitter.com/Marty_P_B/status/1366737347887456260]), (2*) |
| InvestVoyager   | 1             | [(1)](https://twitter.com/sundaywar/status/1366854774864322560?s=20) | 
| Nexo            | 1             | (1*) |


*  Some evidence provided privately to me (6102bitcoin)
** Strong evidence provided privately to me (6102bitcoin)
---
title: "Chain Analysis"
---

| Deep Dive into Chain Analysis Companies. |
|-|

## Introduction

I have written about both [CoinJoin](https://6102bitcoin.com/coinjoin-overview) &  [CoinJoin Flagging](https://6102bitcoin.com/coinjoin-flagging) which is relevant to this discussion.

## Key Points
- Regulated exchanges are going to be increasingly interconnected due to the FATF travel rule requiring the creation of a system to check whether withdrawals are going to another regulated exchange.
- Each chain analysis company is creating a proprietary database which all their customers leverage and many of whom feed data back into.
- Analysis companies may be able to track many more hops than previously expected (dozens rather than ~5).
- Very little criminal activity is actually being performed with bitcoin.
- Monero traceability is "impossible" according to Elliptic.
- It remains unclear how chain analysis companies are treating CoinJoined funds.


## Chain Analysis Justification
Frequently chain analysis companies are portrayed as evil, but those working in these companies go on record publicly (podcasts, conference talks etc.) and make no effort to hide their involvement in this industry.
This doesn't seem like the kind of behavior that you would expect from someone who knowingly does unethical work.

Furthermore, listening to them speak you can hear that they are proud of what they are building and their achievements to date.

Those working on these tools are rational and often clearly intelligent, so the question is - to what can we attribute the stark difference between opinions about the ethics of chain analysis?

It's easy to assume that these individuals are secretly aware that what they are doing is unethical, but that they ignore these concerns in the quest for profit.
This is no doubt true for some people in the world (consider the many examples of shitcoin promoters who knowingly scam uneducated newcomers into buying their shitcoin in an ICO), but I think that this likely over simplifies the situation.

Consider how CEO's of these companies are often happy to talk publicly when they could send an employee to do to same job - this suggests that they are happy to be publicly associated with their company, which they wouldn't be if they thought their company was evil.

It appears that at least some of those working for these companies view their actions as being (in aggregate) ethical - they point to the truly evil individuals who have been caught by law enforcement following analytics made possible by their analytics software.

It could be that those working for these companies simply identify that there is market demand for the product that they are building and haven't seriously considered the ethical issues.
They could easily neutralize any pangs of guilt about the ethics of their actions by the age old Justification of "if I don't do it, someone else will anyway".

In reality I imagine that it is some combination of the above which allow those working at chain analysis companies to justify their actions.

> *People will commit crimes for money, and will need to move/launder that money - and some will use bitcoin. There will likely always be some centralized intermediaries in crypto - and they will have a responsibility to detect and help prevent this.* - Elliptic Founder Tom Robinson ([Tweet](http://archive.is/zWCYx) & [Archive](https://twitter.com/tomrobin/status/1229122631162527744))

## Privacy Justification

Pervasive 'KYC' is a modern invention.
You shouldn't need to provide any of this information.
If you have committed a crime then law enforcement can use real world investigation to catch you.

The argument for private value transfer is exactly the same as the argument for private communication.

It seems bizarre to think that criminals can **only** be caught at the point of spending the proceeds of their criminal acts. Particularly given that if you are focused on catching criminals when they attempt to spend the proceeds of a crime then you miss the opportunities to **prevent** the crime actually occurring.

Yes, catching criminals might be **easier** if law enforcement can spy on everyone's communication (or payments) but if this is not an option they can (and will) get convictions using investigative techniques.

Law enforcement can (and should) be done without destroying freedoms.

## Trends
- Scale of money laundering using bitcoin is increasing, though this could be because bitcoin use in general is increasing or because the ability to detect money laundering is increasing.
- Centralized Mixers are becoming less commonly used due to concerns about honeypots and takedowns, increasingly easy to use non-custodial mixing tools (JoinMarket/Wasabi/Whirlpool) and increasing use of 'privacy coins'.
- 'Privacy Coins' are becoming more commonly used (but are still used far less frequently used then bitcoin  owing to its high liquidity and track record).
- Monero is used far more then ZCash on Darknet Markets - this is likely due to distrust of the project owing to the close ties with banks, strange occurrences (phone recording) in the setup ceremony, the dev fund, the default use of non-private transactions and the more grassroots and anonymous development of Monero.
- Criminals may increasingly keep the proceeds of their funds in bitcoin (rather than 'Cashing out') given that risk of getting caught appears to greatly increase when interfacing with the legacy systems.

## Questions
- Are bitcoin funds which have been CoinJoined as (or more) difficult to trace as Monero, and why.

# How Chain Analysis Works

## Low Level Functionality
These are a number of primitive rules (heuristics) which analytics companies use to attempt to analyse the large number of bitcoin transactions and funds through transactions (e.g. when an output is likely a payment, and when it's likely change). Additionally there are a number of non-blockchain methods which they could (and may currently) use to link addresses into clusters and to link addresses to other metadata (like IP addresses).

- Heuristics
  - Common-Input-Ownership
  - Change-Address-Detection
    - Address-Reuse
    - Wallet-Fingerprinting
    - Round-Numbers
    - Fee-Bumping
    - Unnecessary-Input
    - Send-to-Script-Type
    - Output-Ordering
  - Transaction-Graph
  - Taint-analysis
  - Amount
  - Full-Coin-spend
  - Mystery-Shopper
  - Forced-Address-Reuse
  - Amount-Correlation
  - Timing-Correlation
- Traffic Analysis (Sybil Attack on Nodes / Running Electrum Servers)
- 3rd Party Lookup (Running wallets / buying data from those running wallets which connect to a single server)  
- Block Explorer
- Public Information (Blockchain, Twitter, Bitcointalk, Reddit)
- Private Information (Exchange details)
- User submitted data (e.g. Reddit posts, Bitcointalk accounts, Twitter accounts)

See [bitcoin wiki / privacy](https://en.bitcoin.it/wiki/Privacy#Unnecessary_input_heuristic/#change_address_detection) for more.

## Mid Level Functionality
From the low level functionality the chain analysis company is able to develop a deeper understanding of the movement of funds through the chain.

- Fund Tracing aiming to identify:
  - Ultimate source of funds
  - Ultimate destination of funds
  - Intermediary addresses
- Linking of funds to real world profiles
- Proximity of funds to an illicit actor or prohibited activities
- Clustering of both addresses and users
- Risk Scoring (Incoming Transactions)
- Risk Scoring (Outgoing Transactions)

## High Level Functionality
Ultimately the chain analysis software allows VASP's (Virtual Asset Service Providers) to meet legal requirements (e.g. FATF & AML5).

FATF Requires VASP's to meet the following requirements;

1. **Transaction Monitoring** - Monitor customer transactions (in an automated way if operating at scale) and evaluate based on risk. The analysis should extend beyond the VASP & customer.
2. **The Travel Rule** - FATF Recommendation 16 requires that when one VASP sends funds to another VASP they must also send the following information for BOTH customer & beneficiary; Name and identity of originating & Account ID (for example wallet address). The issue here is the 'VASP discovery problem' - the sending VASP currently doesn't know when funds are being sent to another VASP.
It appears that work is being done to create a sharing platform / protocol to enable VASP's to meet this requirement by communicating whether a particular address is a receiving address for ANY VASP.

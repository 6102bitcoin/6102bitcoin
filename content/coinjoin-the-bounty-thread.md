---
title: "CoinJoin. Part I: The Bounty Thread"
---

This is a summary of the BitcoinTalk thread which was started by Greg Maxwell back in 2013 in order to encourage development of implementations of CoinJoin. A 2of3 multisig [donation address](https://blockstream.info/address/3M8XGFBKwkf7miBzpkU3x2DoWwAVrD1mhk) was created by Greg, Theymos and Pieter Wuille.

Interesting to note that as of today (2019–04–06) no payment has ever been made from this address (except to consolidate funds when fees were low).

{{< figure src="/img/coinjoin-the-bounty-thread-01.png" alt="" position="center" style="border-radius: 8px;" caption="Historic Donation Address Balance ([bitinfocharts](https://bitinfocharts.com/bitcoin/address/3M8XGFBKwkf7miBzpkU3x2DoWwAVrD1mhk))" captionPosition="centre" captionStyle="color: grey;" >}}

A recent [comment](https://www.reddit.com/r/Bitcoin/comments/b8xgz7/nopara73_reapplies_for_the_46_btc_bounty_for_his/ek95nbo/) by Theymos suggest that there may be payouts from the donated funds which now total 46.4 BTC (over $200k) — watch this space!

* * *

**Part I**
===========


* * *

2013 : Genesis
==============

On 2013–08–22 Greg (Maxwell) wrote up an explanation of CoinJoins \[[1](https://bitcointalk.org/index.php?topic=279249.0)\] and posted a bitcoin address to collect funds for a bounty to be used to encourage development of a practical implementation of CoinJoin.

{{< figure src="/img/coinjoin-the-bounty-thread-02.png" alt="" position="center" style="border-radius: 8px;" caption="Image from the [original thread](https://bitcointalk.org/index.php?topic=279249.msg2983902#msg2983902) \[1\]" captionPosition="centre" captionStyle="color: grey;" >}}

It was stated that ‘**The bounty fund will pay out as funds are available according to the signers best judgement for completed work proposed in this thread that furthers the goal of making improved transaction privacy a practical reality for Bitcoin users**’. As such, it isn’t a single payout bounty, it was intended to pay out on an ongoing basis as work was completed.

Just 5 days later (2013–08–27) ‘genjix’ (Amir Taaki) was the first to try and claim the bounty with a proof of concept \[[2](https://bitcointalk.org/index.php?topic=279249.msg3016952#msg3016952)\] he had developed with ‘Pablo’. A couple of days later (2013–08–29) he added a public ‘lobby’ to serve as a meeting point and flexible mixing amounts. He posted a video showing the system at work \[[3](https://www.youtube.com/watch?v=rr6DeziHdFs)\]. A simple explanation of what was done was posted back on the main thread \[[4](https://bitcointalk.org/index.php?topic=279249.msg3022039#msg3022039)\]. Though Greg commented in thread **there was no mention of a payout.**

The next day (2013–08–28) ‘Tom Scholl’ pointed out \[[5](https://bitcointalk.org/index.php?topic=279249.msg3029760#msg3029760)\] that 3 months prior he had worked on a fully decentralized solution called ‘BitPrivacy’ which he posted about on bitcointalk \[[6](https://bitcointalk.org/index.php?topic=200952.0)\]. A day later (2013–08–29) ‘Tom Scholl’ placed his claim to part of the bounty \[[7](https://bitcointalk.org/index.php?topic=279249.msg3035441#msg3035441)\].

Greg posted \[[8](https://bitcointalk.org/index.php?topic=279249.msg3037882#msg3037882)\] to clarify that ‘**My main criteria is that work done be actually usable by someone for something … show me the code**’, ‘**the whole idea is to flow some funds from people who want to see this exist to people who are working on making it exist and everyone leaving happy**’, ‘**And yes, I need to pay out some bounties to the work done by people so far**’.

The next day (2013–08–30) ‘maaku; posted \[[9](https://bitcointalk.org/index.php?topic=279249.msg3045937#msg3045937)\] his work \[[10](https://github.com/maaku/coinjoin)\] called ‘CoinJoin’ on the topic.

Two days later (2013–09–01) Olivier Coutu posted \[[11](https://bitcointalk.org/index.php?topic=279249.msg3057216#msg3057216)\] a link to his presentation \[[12](http://www.youtube.com/watch?v=6hc8qaR_Fok&list=PLUOP0P68GJ3BGjfqoLLnzAefk3ZzXQtJ7&index=35)\] from the Bitcoin 2013 conference on Decentralized Mixers for Bitcoin as well as the .pdf \[[13](https://www.dropbox.com/s/nvkvo1dl3xif87v/PresentationBitcoin2013.pdf)\] of his slides.

Over a week later (2013–09–10) maaku posted \[[14](https://bitcointalk.org/index.php?topic=279249.msg3124886#msg3124886)\] the link to the thread \[[15](https://bitcointalk.org/index.php?topic=291283.0)\] he made the day earlier where he was looking to crowdfunded donations (85 BTC). _Side note, two weeks later (2013–09–25) maaku posted \[_[_16_](https://bitcointalk.org/index.php?topic=291283.msg3233380#msg3233380)_\] saying that he had not received any donations. His last post in the crowdfunding thread was 4 months later, a month after he pushed the last commit to the project’s github page \[_[_17_](https://github.com/maaku/coinjoin)_\]._

2013–09–11 greg posted \[[18](https://bitcointalk.org/index.php?topic=279249.msg3128495#msg3128495)\] that he was enjoying Peter Todd’s dust-b-gone \[[19](https://github.com/petertodd/dust-b-gone/)\] tool.

2013–10–10 greg posted a great insight — ‘**Above all other criteria widespread usage is what makes the difference between your “plausible denyability” and whatever you’d call actual “anonymity**”.’ \[[20](https://bitcointalk.org/index.php?topic=279249.msg3343828#msg3343828)\]

2013–10–19 user ‘n8rwJeTt8TrrLKPa55’ pointed out \[[21](https://bitcointalk.org/index.php?topic=279249.msg3370833#msg3370833)\] a post \[[22](https://bitcointalk.org/index.php?topic=40264.msg3367854#msg3367854)\] by blockchain.info announcing that their coinjoin scheme (called Sharedcoin). It used a centralized server to co-ordinate transactions but it had no access to funds. The source code was also pushed to GitHub \[[23](https://github.com/blockchain/My-Wallet/blob/master/sharedcoin.js)\].

2013–11–03 ‘piuk’ announced that the blockchain.info coinjoin implementation (Sharedcoin) was available by default in their wallet. It mixed both with other users funds and a pool provided by blockchain.info to reduce wait times and ‘reduce transaction taint’.

2013–11–09 laanwj opened an issue \[[24](https://github.com/bitcoin/bitcoin/issues/3226)\] on the bitcoin QT (now bitcoin core) github suggesting that ‘it would be useful to support coinjoin in the client and GUI’. No-one took up the challenge and the closest anyone got to suggesting something that could be implemented was chris-belcher who, **3 years later**, suggested \[[25](https://github.com/bitcoin/bitcoin/issues/3226#issuecomment-211656934)\] a way of integrating Bitcoin-qt & joinmaket, in the same post he pointed out a way to send coinjoins from Bitcoin Core wallet using joinmarket sendpayment.py script.

2013–11–14 a user posted \[[26](https://bitcointalk.org/index.php?topic=279249.msg3583624#msg3583624)\] a link \[[27](https://www.reddit.com/r/Bitcoin/comments/1qmhkh/coinjoin_fundraising_drive/)\] to a reddit thread where further funds were being raised. At the time the post was made the bounty stood at ~16 BTC. Interestingly there were some users who expressed difficulty in sending to the donation address because it was a p2SH address which bitcoinj wallets (Armoury & MT Gox) could not send to.

2013–11–15 Theymos agreed to match donations over the proceeding 30 days up to a limit of 5 BTC (which was reached) \[[28](https://bitcointalk.org/index.php?topic=279249.msg3586519#msg3586519)\]. Within the next 4 days the donation address balance doubled to ~32 BTC

2013–11–15 ‘coinft’ made the suggestion \[[29](https://bitcointalk.org/index.php?topic=279249.msg3587715#msg3587715)\] that if miners operated liquid CoinJoin pools through which they passed all their new block rewards a large fraction of bitcoin would be ‘tainted’, effectively making blacklisting tainted coins impractical.

2013–11–22 ‘BurtW’ pledged to donate 5 BTC as soon as the fund reached 36 BTC, and looking at the blockchain it looks like he did \[[30](https://blockstream.info/tx/218c78d6a215f9503787c6eaed7a2dd484d4448fca411846040b4363e9ee4269)\].

2013–12–11 ‘andytoshi’ announced \[[31](https://bitcointalk.org/index.php?topic=279249.msg3915953#msg3915953)\] development of a tool \[[32](https://github.com/apoelstra/coinjoin)\] ‘to make CoinJoining easier to do’. It required manual sending of a raw tx from each user to an individual acting as coordinator who would run a command to create an unsigned merged tx. This then had to be sent back to each individual who would sign and send back. The coordinator would then manually enter these signed tx’s and submit to the network.

* * *

2014
====

2014–02–02 ‘themgp’ announced \[[33](https://bitcointalk.org/index.php?topic=279249.msg4886644#msg4886644)\] development of a tool \[[34](https://github.com/michaelgpearce/coinmux)\] called Coinmux in which peers communicate using JSON messages. Within 4 days it had been tested on mainnet \[[35](https://bitcointalk.org/index.php?topic=279249.msg4967183#msg4967183)\] though it was soon found to be susceptible to IP snooping \[[36](https://bitcointalk.org/index.php?topic=279249.msg5037566#msg5037566)\]. 10 days later (2014–12–16) themgp added a GUI \[[37](https://bitcointalk.org/index.php?topic=279249.msg5186922#msg5186922)\].

**2014–03–30 maaku asked when bitcoin would be distributed to CoinJoin developers \[**[**38**](https://bitcointalk.org/index.php?topic=279249.msg5986254#msg5986254)**\].**

**2014–04–01 greg replied \[**[**39**](https://bitcointalk.org/index.php?topic=279249.msg6010603#msg6010603)**\] stating that “Any payouts would need to be discussed with the other signers, but my thinking had been to pay most of it to to the most substantive complete and usable implementation, and partial amounts to smaller efforts”.**

2014–05–02 ‘caedes’ posted \[[40](https://bitcointalk.org/index.php?topic=279249.msg6509800#msg6509800)\] about darkwallet’s CoinJoin efforts.

2014–06–06 ‘laurentmt’ posted \[[41](https://bitcointalk.org/index.php?topic=279249.msg7170950#msg7170950)\] in detail some thoughts on tx entropy and address identification.

2014–06–10 ‘justusranvier’ posted \[[42](https://bitcointalk.org/index.php?topic=279249.msg7225629#msg7225629)\] a link to coinjoinsoduku’s announcement \[[43](http://www.coinjoinsudoku.com/advisory/)\] that they were soon going to release a tool to de-anonymise SharedCoin tx’s (blockchain.info’s CoinJoin offering). Indeed, the tool was later released \[[44](https://github.com/kristovatlas/coinjoin-sudoku)\]. The details are interesting but out of scope for this article.

2014–08–08 ‘belcher’ posted \[[45](https://bitcointalk.org/index.php?topic=279249.msg8139466#msg8139466)\] that he had coded a simple implementation of CoinJoin (‘CoinJumble’) and linked to the announcement thread \[[46](https://bitcointalk.org/index.php?topic=730321.msg8254585)\] in which the link to the project’s github page was posted \[[47](https://github.com/chris-belcher/coinjumble)\]. Soon after he acknowledged that an electrum plugin would less likely to result in lost funds (with users not needing to manage exposed private keys).

2014–10–01 ‘dillpicklechips’ posted \[[48](https://bitcointalk.org/index.php?topic=279249.msg9042932#msg9042932)\] some links about CoinShuffle including a video explanation \[[49](https://www.youtube.com/watch?v=YDGUUtDqNV0)\] & GitHub links \[[50](https://github.com/bryanvu/coinshuffle-server)\],\[[51](https://github.com/bryanvu/coinshuffle-sim)\],\[[52](https://github.com/bryanvu/bitcoinjslib-wallet)\].

2014–10–30 Belcher posted \[[53](https://bitcointalk.org/index.php?topic=279249.msg9384411#msg9384411)\] how to improve darkwallet’s CoinJoin. His proposal was to ‘Pay the coinjoin makers. They will put up offers to do coinjoin along with a fee they ask’.

* * *

**2015**
========

2015–01–09 Belcher posted \[[54](https://bitcointalk.org/index.php?topic=279249.msg10096777#msg10096777)\] a link \[[55](https://bitcointalk.org/index.php?topic=919116.msg10096718)\] to his announcement of ‘JoinMarket’ as well as a link to the GitHub page \[[56](https://github.com/chris-belcher/joinmarket)\].

2015–05–08 Belcher posted \[[57](https://bitcointalk.org/index.php?topic=279249.msg11316527#msg11316527)\] an announcement that JoinMarket was live on mainnet.

2015–06–12 ‘Mexles’ posted \[[58](https://bitcointalk.org/index.php?topic=279249.msg11599760#msg11599760)\] a link \[[59](https://bitcointalk.org/index.php?topic=1085436.msg11597427)\] to his work on Compact Confidential Transactions which greg described as super exciting and important \[[60](https://bitcointalk.org/index.php?topic=1085436.msg11646936#msg11646936)\], though there was no code. A problem was identified by Andrew Poelstra which resulted in the proofs being less compact than initially hoped. I tried to follow the thread but it gets … complicated, see photo

{{< figure src="/img/coinjoin-the-bounty-thread-03.png" alt="" position="center" style="border-radius: 8px;" caption="[TPTB\_need\_war](https://bitcointalk.org/index.php?action=profile;u=504237) lost me by this point \[[61](https://bitcointalk.org/index.php?topic=1085436.msg12964946#msg12964946)\]" captionPosition="centre" captionStyle="color: grey;" >}}



* * *

2016
====

2016–05–23 belcher posted \[[62](https://bitcointalk.org/index.php?topic=279249.msg14938401#msg14938401)\] a link to his paper \[[63](http://arxiv.org/abs/1605.06369)\] on address closures and clustering. **He also commented that he had reached out to theymos, pieter and greg 6 months prior requesting some of the bounty.**

2017
====

2017–12–12 **greg posted \[**[**64**](https://bitcointalk.org/index.php?topic=279249.msg26230669#msg26230669)**\] that the address had been consolidated to take advantage of low fees on the network.**

**\# note. It looks like the BCASH in the wallet was moved on 2017–05–08.**

2017–12–18 wintercooled posted \[[65](https://bitcointalk.org/index.php?topic=279249.msg26563793#msg26563793)\] that he and Adam Ficsor (nopara73) were looking for 100 testers for ‘an implementation of a Chaumian CoinJoin mixer and client wallet using the ZeroLink framework and HiddenWallet’ \[[66](https://github.com/nopara73/ZeroLink)\],\[[67](https://github.com/nopara73/HiddenWallet/blob/master/HiddenWallet.Documentation/TestingTheZeroLinkMixer.md)\]

**2018**
========

2018–10–17 nopara73 posted \[[68](https://bitcointalk.org/index.php?topic=279249.msg46988492#msg46988492)\] that he was applying for a part of the bounty. He provided a very comprehensive list of all of the things that he has done to improve bitcoin privacy.

2018–12–25 RHavar posted \[[69](https://bitcointalk.org/index.php?topic=279249.msg48881217#msg48881217)\] that he had created bustapay \[[70](https://github.com/bitcoin/bips/blob/master/bip-0079.mediawiki)\],\[[71](https://github.com/rhavar/bustapay)\]

**2019**
========

2019–04–03 **nopara73 posted \[**[**72**](https://bitcointalk.org/index.php?topic=279249.msg50438943#msg50438943)**\] again and noted that he had not recieved a reply from theymos or greg (though he had recieved one from pieter). He hilighted that Wasabi had mixed 22941 BTC. He explained all of the updates to the software.**

2019–04–06 ‘coiner.de’ posted \[[73](https://bitcointalk.org/index.php?topic=279249.msg50487160#msg50487160)\] that he had got a reaction from theymos \[[74](https://www.reddit.com/r/Bitcoin/comments/b8xgz7/nopara73_reapplies_for_the_46_btc_bounty_for_his/ek95nbo/)\]. In the linked reddit thread theymos said — **‘We’ve been discussing whether wasabi/joinmarket deserve some of the bounty. Personally, I think that wasabi does deserve some of the bounty.’**

References
==========

\[1\] [https://bitcointalk.org/index.php?topic=279249.0](https://bitcointalk.org/index.php?topic=279249.0)  
\[2\] [https://bitcointalk.org/index.php?topic=279249.msg3016952#msg3016952](https://bitcointalk.org/index.php?topic=279249.msg3016952#msg3016952)  
\[3\] [https://www.youtube.com/watch?v=rr6DeziHdFs](https://www.youtube.com/watch?v=rr6DeziHdFs)  
\[4\] [https://bitcointalk.org/index.php?topic=279249.msg3022039#msg3022039](https://bitcointalk.org/index.php?topic=279249.msg3022039#msg3022039)  
\[5\] [https://bitcointalk.org/index.php?topic=279249.msg3029760#msg3029760](https://bitcointalk.org/index.php?topic=279249.msg3029760#msg3029760)  
\[6\] [https://bitcointalk.org/index.php?topic=200952.0](https://bitcointalk.org/index.php?topic=200952.0)  
\[7\] [https://bitcointalk.org/index.php?topic=279249.msg3035441#msg3035441](https://bitcointalk.org/index.php?topic=279249.msg3035441#msg3035441)  
\[8\] [https://bitcointalk.org/index.php?topic=279249.msg3037882#msg3037882](https://bitcointalk.org/index.php?topic=279249.msg3037882#msg3037882)  
\[9\] [https://bitcointalk.org/index.php?topic=279249.msg3045937#msg3045937](https://bitcointalk.org/index.php?topic=279249.msg3045937#msg3045937)  
\[10\] [https://github.com/maaku/coinjoin](https://github.com/maaku/coinjoin)  
\[11\] [https://bitcointalk.org/index.php?topic=279249.msg3057216#msg3057216](https://bitcointalk.org/index.php?topic=279249.msg3057216#msg3057216)  
\[12\] [http://www.youtube.com/watch?v=6hc8qaR\_Fok&list=PLUOP0P68GJ3BGjfqoLLnzAefk3ZzXQtJ7&index=35](http://www.youtube.com/watch?v=6hc8qaR_Fok&list=PLUOP0P68GJ3BGjfqoLLnzAefk3ZzXQtJ7&index=35)  
\[13\] [https://www.dropbox.com/s/nvkvo1dl3xif87v/PresentationBitcoin2013.pdf](https://www.dropbox.com/s/nvkvo1dl3xif87v/PresentationBitcoin2013.pdf)  
\[14\] [https://bitcointalk.org/index.php?topic=279249.msg3124886#msg3124886](https://bitcointalk.org/index.php?topic=279249.msg3124886#msg3124886)  
\[15\] [https://bitcointalk.org/index.php?topic=291283.0](https://bitcointalk.org/index.php?topic=291283.0)  
\[16\] [https://bitcointalk.org/index.php?topic=291283.msg3233380#msg3233380](https://bitcointalk.org/index.php?topic=291283.msg3233380#msg3233380)  
\[17\] [https://github.com/maaku/coinjoin](https://github.com/maaku/coinjoin)  
\[18\] [https://bitcointalk.org/index.php?topic=279249.msg3128495#msg3128495](https://bitcointalk.org/index.php?topic=279249.msg3128495#msg3128495)  
\[19\] [https://github.com/petertodd/dust-b-gone/](https://github.com/petertodd/dust-b-gone/)  
\[20\] [https://bitcointalk.org/index.php?topic=279249.msg3343828#msg3343828](https://bitcointalk.org/index.php?topic=279249.msg3343828#msg3343828)  
\[21\] [https://bitcointalk.org/index.php?topic=279249.msg3370833#msg3370833](https://bitcointalk.org/index.php?topic=279249.msg3370833#msg3370833)  
\[22\] [https://bitcointalk.org/index.php?topic=40264.msg3367854#msg3367854](https://bitcointalk.org/index.php?topic=40264.msg3367854#msg3367854)  
\[23\] [https://github.com/blockchain/My-Wallet/blob/master/sharedcoin.js](https://github.com/blockchain/My-Wallet/blob/master/sharedcoin.js)  
\[24\] [https://github.com/bitcoin/bitcoin/issues/3226](https://github.com/bitcoin/bitcoin/issues/3226)  
\[25\] [https://github.com/bitcoin/bitcoin/issues/3226#issuecomment-211656934](https://github.com/bitcoin/bitcoin/issues/3226#issuecomment-211656934)  
\[26\] [https://bitcointalk.org/index.php?topic=279249.msg3583624#msg3583624](https://bitcointalk.org/index.php?topic=279249.msg3583624#msg3583624)  
\[27\] [https://www.reddit.com/r/Bitcoin/comments/1qmhkh/coinjoin\_fundraising\_drive/](https://www.reddit.com/r/Bitcoin/comments/1qmhkh/coinjoin_fundraising_drive/)  
\[28\] [https://bitcointalk.org/index.php?topic=279249.msg3586519#msg3586519](https://bitcointalk.org/index.php?topic=279249.msg3586519#msg3586519)  
\[29\] [https://bitcointalk.org/index.php?topic=279249.msg3587715#msg3587715](https://bitcointalk.org/index.php?topic=279249.msg3587715#msg3587715)  
\[30\] tx:218c78d6a215f9503787c6eaed7a2dd484d4448fca411846040b4363e9ee4269  
\[31\] [https://bitcointalk.org/index.php?topic=279249.msg3915953#msg3915953](https://bitcointalk.org/index.php?topic=279249.msg3915953#msg3915953)  
\[32\] [https://github.com/apoelstra/coinjoin](https://github.com/apoelstra/coinjoin)  
\[33\] [https://bitcointalk.org/index.php?topic=279249.msg4886644#msg4886644](https://bitcointalk.org/index.php?topic=279249.msg4886644#msg4886644)  
\[34\] [https://github.com/michaelgpearce/coinmux](https://github.com/michaelgpearce/coinmux)  
\[35\] [https://bitcointalk.org/index.php?topic=279249.msg4967183#msg4967183](https://bitcointalk.org/index.php?topic=279249.msg4967183#msg4967183)  
\[36\] [https://bitcointalk.org/index.php?topic=279249.msg5037566#msg5037566](https://bitcointalk.org/index.php?topic=279249.msg5037566#msg5037566)  
\[37\] [https://bitcointalk.org/index.php?topic=279249.msg5186922#msg5186922](https://bitcointalk.org/index.php?topic=279249.msg5186922#msg5186922)  
\[38\] [https://bitcointalk.org/index.php?topic=279249.msg5986254#msg5986254](https://bitcointalk.org/index.php?topic=279249.msg5986254#msg5986254)  
\[39\] [https://bitcointalk.org/index.php?topic=279249.msg6010603#msg6010603](https://bitcointalk.org/index.php?topic=279249.msg6010603#msg6010603)  
\[40\] [https://bitcointalk.org/index.php?topic=279249.msg6509800#msg6509800](https://bitcointalk.org/index.php?topic=279249.msg6509800#msg6509800)  
\[41\] [https://bitcointalk.org/index.php?topic=279249.msg7170950#msg7170950](https://bitcointalk.org/index.php?topic=279249.msg7170950#msg7170950)  
\[42\] [https://bitcointalk.org/index.php?topic=279249.msg7225629#msg7225629](https://bitcointalk.org/index.php?topic=279249.msg7225629#msg7225629)  
\[43\] [http://www.coinjoinsudoku.com/advisory/](http://www.coinjoinsudoku.com/advisory/)  
\[44\] [https://github.com/kristovatlas/coinjoin-sudoku](https://github.com/kristovatlas/coinjoin-sudoku)  
\[45\] [https://bitcointalk.org/index.php?topic=279249.msg8139466#msg8139466](https://bitcointalk.org/index.php?topic=279249.msg8139466#msg8139466)  
\[46\] [https://bitcointalk.org/index.php?topic=730321.msg8254585](https://bitcointalk.org/index.php?topic=730321.msg8254585)  
\[47\] [https://github.com/chris-belcher/coinjumble](https://github.com/chris-belcher/coinjumble)  
\[48\] [https://bitcointalk.org/index.php?topic=279249.msg9042932#msg9042932](https://bitcointalk.org/index.php?topic=279249.msg9042932#msg9042932)  
\[49\] [https://www.youtube.com/watch?v=YDGUUtDqNV0](https://www.youtube.com/watch?v=YDGUUtDqNV0)  
\[50\] [https://github.com/bryanvu/coinshuffle-server](https://github.com/bryanvu/coinshuffle-server)  
\[51\] [https://github.com/bryanvu/coinshuffle-sim](https://github.com/bryanvu/coinshuffle-sim)  
\[52\] [https://github.com/bryanvu/bitcoinjslib-wallet](https://github.com/bryanvu/bitcoinjslib-wallet)  
\[53\] [https://bitcointalk.org/index.php?topic=279249.msg9384411#msg9384411](https://bitcointalk.org/index.php?topic=279249.msg9384411#msg9384411)  
\[54\] [https://bitcointalk.org/index.php?topic=279249.msg10096777#msg10096777](https://bitcointalk.org/index.php?topic=279249.msg10096777#msg10096777)  
\[55\] [https://bitcointalk.org/index.php?topic=919116.msg10096718](https://bitcointalk.org/index.php?topic=919116.msg10096718)  
\[56\] [https://github.com/chris-belcher/joinmarket](https://github.com/chris-belcher/joinmarket)  
\[57\] [https://bitcointalk.org/index.php?topic=279249.msg11316527#msg11316527](https://bitcointalk.org/index.php?topic=279249.msg11316527#msg11316527)  
\[58\] [https://bitcointalk.org/index.php?topic=279249.msg11599760#msg11599760](https://bitcointalk.org/index.php?topic=279249.msg11599760#msg11599760)  
\[59\] [https://bitcointalk.org/index.php?topic=1085436.msg11597427](https://bitcointalk.org/index.php?topic=1085436.msg11597427)  
\[60\] [https://bitcointalk.org/index.php?topic=1085436.msg11646936#msg11646936](https://bitcointalk.org/index.php?topic=1085436.msg11646936#msg11646936)  
\[61\] [https://bitcointalk.org/index.php?topic=1085436.msg12964946#msg12964946](https://bitcointalk.org/index.php?topic=1085436.msg12964946#msg12964946)  
\[62\] [https://bitcointalk.org/index.php?topic=279249.msg14938401#msg14938401](https://bitcointalk.org/index.php?topic=279249.msg14938401#msg14938401)  
\[63\] [http://arxiv.org/abs/1605.06369](http://arxiv.org/abs/1605.06369)  
\[64\] [https://bitcointalk.org/index.php?topic=279249.msg26230669#msg26230669](https://bitcointalk.org/index.php?topic=279249.msg26230669#msg26230669)  
\[65\] [https://bitcointalk.org/index.php?topic=279249.msg26563793#msg26563793](https://bitcointalk.org/index.php?topic=279249.msg26563793#msg26563793)  
\[66\] [https://github.com/nopara73/ZeroLink](https://github.com/nopara73/ZeroLink)  
\[67\] [https://github.com/nopara73/HiddenWallet/blob/master/HiddenWallet.Documentation/TestingTheZeroLinkMixer.md](https://github.com/nopara73/HiddenWallet/blob/master/HiddenWallet.Documentation/TestingTheZeroLinkMixer.md)  
\[68\] [https://bitcointalk.org/index.php?topic=279249.msg46988492#msg46988492](https://bitcointalk.org/index.php?topic=279249.msg46988492#msg46988492)  
\[69\] [https://bitcointalk.org/index.php?topic=279249.msg48881217#msg48881217](https://bitcointalk.org/index.php?topic=279249.msg48881217#msg48881217)  
\[70\] [https://github.com/bitcoin/bips/blob/master/bip-0079.mediawiki](https://github.com/bitcoin/bips/blob/master/bip-0079.mediawiki)  
\[71\] [https://github.com/rhavar/bustapay](https://github.com/rhavar/bustapay)  
\[72\] [https://bitcointalk.org/index.php?topic=279249.msg50438943#msg50438943](https://bitcointalk.org/index.php?topic=279249.msg50438943#msg50438943)  
\[73\] [https://bitcointalk.org/index.php?topic=279249.msg50487160#msg50487160](https://bitcointalk.org/index.php?topic=279249.msg50487160#msg50487160)  
\[74\] [https://www.reddit.com/r/Bitcoin/comments/b8xgz7/nopara73\_reapplies\_for\_the\_46\_btc\_bounty\_for\_his/ek95nbo/](https://www.reddit.com/r/Bitcoin/comments/b8xgz7/nopara73_reapplies_for_the_46_btc_bounty_for_his/ek95nbo/)

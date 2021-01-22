---
title: "Hodl Privacy FAQ"
---

## Index
- [Motivation](#motivation)
- [Potential Data Leaks](#potential-data-leaks)
    - [Block Explorers](#block-explorers)
    - [Exact Amount Conversion](#exact-amount-conversion)
    - [Browser Plugins](#browser-plugins)
    - [Hardware Wallet Software](#hardware-wallet-software)
    - [Wallet with Email 2FA](#wallet-with-email-2fa)
    - [Limited Block Download](#limited-block-download)
    - [HTTP](#http)
    - [Email Confirmations](#email-confirmations)

## Motivation
I saw a thought provoking [post](https://twitter.com/ercwl/status/1136211928873938944) on Twitter;
> "A lot of people now say that Bitcoin is completely transparent and even worse than the banking system for privacy. But answer me this: **if I go out on the street and sell my fiat cash for BTC which I store on a new wallet, which corporation can know my net worth?**"

The answer is that it depends very much on what tools/services you use.
- With **careful** use of the best bitcoin tools it's **not possible** for anyone to know how much bitcoin you have.
- With **careless** use of the worst (& often most common tools) it **is possible** that a picture can be built up over time by a sufficiently motivated attacker.

Most of the identified potential data leaks don't link your coins directly to you as an individual; they link to data that can be linked to you (IP address for example). Often it's the combination of more than one of these data sources that is problematic.

**The good news**: The default ways of using bitcoin do appear to be improving over time, and the best ways of using bitcoin are becoming very sophisticated. This FAQ will arm you with the tools to hodl privately.

---
### Potential Data Leaks
For each potential data leak that I have identified I have listed Action | Data Leak | Mitigation.
- **Action**: How you might accidentally expose yourself to a data leak
- **Data Leak**: What information you may leak and to whom
- **Mitigation**: How you can limit/avoid the data leak

---
## Block Explorers

#### Action:
You use an online block explorer to check whether you have received payment

#### Data Leak:
The company/individual running the block explorer can link any info you enter into the site (e.g. bitcoin address / transaction id) to your IP address. If you check whether a bitcoin address has a bitcoin balance it is a weak-mid strength signal that it's your bitcoin address.. If you check whether a bitcoin address has a bitcoin balance and it has either recently received bitcoin or subsequently soon after checking received bitcoin it is a strong strength signal that it's your bitcoin address.

#### Mitigation:
Access the block explorers via TOR [e.g. [blockstream.info](http://explorerzydxu5ecjrkwceayqybizmpjjznk5izmitf2modhcusuqlid.onion/)] or run your own [block explorer software](https://github.com/janoside/btc-rpc-explorer) which gets data from your own full node.

---
## Exact Amount Conversion

#### Action:
Searching 'What is x.xxxxxxx BTC in $' (or other online conversion tools).

#### Data Leak:
If the amount of bitcoin you search for is a single UTXO and a unique value then the search provider can link your IP address with that coin. If the search provider is google and you are logged in then it's likely that they can link the UTXO to you (they have most of your personal info).

#### Mitigation:
Search with [DuckDuckGo over TOR](http://3g2upl4pq6kufc4m.onion/) | Search with less precision x.xx BTC | Manually Calculate

---
## Browser Plugins

#### Action:
You use a plugin with access to all website data & do one of the above.

#### Data Leak:
Plugin developer gets a copy of the data leaked above (via block explorers or exact amount conversion).

#### Mitigation:
Avoid plugins which have broad access to your web browsing | Use a browser without plugins when doing anything bitcoin related | Use incognito/private browsing when doing anything bitcoin related to disable plugins.

---
## Hardware Wallet Software

#### Action:
You use the wallet software from your hardware wallet provider.

#### Data Leak:
Most hardware wallets come with software that sends your public keys to the servers of the hardware wallet manufacturer. This means that the hardware wallet manufacturer can link your IP address to your coins. If the hardware manufacturer requires you to have an account or share other personal information then this could also be linked to your coins.

#### Mitigation:
Use bitcoin wallet software that doesn't leak data about your coins for example the [electrum](https://electrum.org/#home) wallet with [electrum personal server](https://github.com/chris-belcher/electrum-personal-server) or [wasabi wallet](https://wasabiwallet.io).

---
## Wallet with Email 2FA

#### Action:
You use a wallet with email 2FA that isn't exclusively connected to your own node.

#### Data Leak:
Your email address can be linked to your coins because your wallet leaks information about your coins to the wallet developer’s server along with your IP address (which could be logged when supplying your email address).

#### Mitigation:
Avoid email 2FA (use an alternative like Google Authenticator when possible) for bitcoin wallets and connect your wallet to your own node.

---
## Limited Block Download

#### Action:
You use a light wallet that has unsophisticated clearnet block downloading rules.

#### Data Leak:
Most light wallets download only the blocks that are relevant to your transactions making it easy for someone able to monitor the blocks you download (i.e. your ISP) to to identify the addresses common amongst blocks. Your ISP can then link your internet connection point / IP Address with your coins.

#### Mitigation:
Use a wallet connected to your full node (which downloads **every block** making this attack useless) | Use a privacy preserving wallet (like [wasabi wallet](https://wasabiwallet.io)).

---
## HTTP

#### Action:
You do any of the above things without an encrypted connection to the server you are communicating with (i.e. over http).

#### Data Leak:
Your ISP can intercept all the data from the above leaks.

#### Mitigation:
Only connect via HTTPS (look for the green padlock at the left hand side of the URL).

---
## Email Confirmations

#### Action:
You add to your hodl stash using an online exchange to send to a previously used cold-storage address.

#### Data Leak:
Confirmation emails confirming the withdrawal leak your address to your email provider (i.e. Google/Microsoft). The exchange can also link your email to the address.

#### Mitigation
Disable notifications if possible | Use a dedicated email not connected to your identity.

---

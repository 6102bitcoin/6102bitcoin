---
title: "xpub collision warning"
---

xpubs from different accounts in the same wallet have a significant similarity (12 leading characters in common, excluding 'xpub') and can therefore be associated. If you share multiple xpubs with third parties you should use a unique passphrase rather than using a different account index in the derivation path. 

This is an edge case and it is very likely that it affects no-one. It is not common knowledge and given the increasing sharing of xpubs with exchanges (for automatic withdrawals) this is useful information to be aware of. 

(note: don't use KYC exchanges, use [noKYConly](https://bitcoiner.guide/nokyconly/))

---

How this could be an issue:

0. A user makes a wallet 

1. They use xpub 0 (corresponding to account 0) on a DNM to process withdrawals to cold storage automatically (I doubt any DNM offer this service currently, get in touch if you know one does). 

xpub 0 (m/84'/0'/0'):
xpub6DTSDUqGFofVDYwzd3GNcarScVAn6W7zeSfHyerVPdePdJSyp1uuCmPQu7TezdWVTHn3izyPFEgc7zwWjdHb14tNiXnQE4YyT5cF6NH1VZF

2. They sign up to regulated exchange X and use xpub 1 (corresponding to account 1). 

xpub 1 (m/84'/0'/1'):
xpub6DTSDUqGFofVF7SsHqrBjLd5ZKrPs9eu2GCuT9ryx4gc9WFfqQkXnG9NKUuFsiBcErkEUDT2eisUt9FEVzrY1spvmxNiCehddzc8PiUiKPc

3. A 3 letter agency gets access to the DNM logs and either 
- requests the exchanges in their jurisdiction to check for xpubs starting with `xpub6DTSDUqGFofV`
- has already compelled exchanges to submit xpubs as they are submitted.

4. They identify that an xpub starting with `xpub6DTSDUqGFofV` has been used on exchange X allowing them to identify the DNM vendor.
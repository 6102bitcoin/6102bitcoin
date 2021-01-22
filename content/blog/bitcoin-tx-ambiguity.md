---
title: "Bitcoin tx Ambiguity"
---

| Bitcoin transactions are public, yet regularly ambiguous. Some thoughts. |
|-|

## Introduction

Lots of smart people are working on sophisticated methods of breaking common heuristics.
Here I evaluate the two most basic types of transaction, and suggest some 'low tech' methods of further breaking these heuristics.

I shall make use of tables like this:

| IN_X    | OUT_Y   |
| ------- | ------- |
| Alice   | Bob     |

- IN_X refers to Transaction Input number X
- OUT_Y refers to Transaction Output number Y
- Alice is the owner of IN_X
- Bob is the owner of OUT_Y

Transaction fees are ignored to make it easier to read - assume one of the outputs is reduced slightly in order to provide a transaction fee.

The relative size of outputs is also ignored (for now).

# 1 IN | 1 OUT
Let us analyse a 1 Input, 1 Output Transaction:

```
IN_1  ->  OUT_1
```

## Assuming One Party:

| IN_1    | OUT_1   |
| ------- | ------- |
| Alice   | Alice   |

Alice sends the full amount to herself without any change.
This is a classic send to self.

Example Scenarios:
- Alice is be moving her coins from a hot wallet into cold storage, or vice versa.
- Alice is sending coins from an old wallet to a new wallet.
- Alice is sweeping a bitcoin paper wallet.

## Assuming Two Parties:

| IN_1    | OUT_1   |
| ------- | ------- |
| Alice   | Bob     |

Alice sends the full amount to Bob without any change.

Example Scenarios:
- Alice is be buying some 'credits' at Bob's company (e.g. API calls) where she can specify the amount she spends and Bob will credit her account accordingly.
- Alice is selling some bitcoin for cash where she can specify how much bitcoin she is selling.
- Alice is sending a coin to Bob, and in a separate transaction receiving a coin from Bob such that Alice pays Bob in an undetectable way.

## 1 IN | 1 OUT Suggestions

There are two ways to interpret even this basic transaction.
The most common is likely the first, given that few services allow depositing an arbitrary amount.

As such, increasing the number of two party 1 Input 1 Output transactions would help break this assumption.
- Raise awareness of the (trustworthy) services that have 'credit' accounts
- Encourage more (trustworthy) services to allow this type of 'credit' arrangement
- Invent alternate methods of paying with a full coin (change back on in a batched transaction or over lightning?)
- Encourage users who trust each other to swap coins (and pay the difference via a side channel e.g. lightning)

# 1 IN | 2 OUT
Let us analyse the following 1 Input, 2 Output Transaction.

```
IN_1  ->  OUT_1
      ->  OUT_2
```

## Assuming One Party:

| IN_1    | OUT_1   | OUT_2   |
| ------- | ------- | ------- |
| Alice   | Alice   | Alice   |

Alice sends the full amount to herself with change.

Example Scenarios:
- Alice is be moving a precise bitcoin value (e.g. 0.1 BTC) from a hot wallet without coin control into cold storage.
- Alice makes a TX0 transaction with whirlpool

## Assuming Two Parties:

| Scenario| IN_1    | OUT_1   | OUT_2   |
| ------- | ------- | ------- | ------- |
| A       | Alice   | Alice   | Bob     |
| B       | Alice   | Bob     | Bob     |

Scenario A -  Alice sends some to Bob, and some to herself

Example Scenarios:
- Alice is be paying Bob for a service where Bob specifies how much bitcoin Alice should send (e.g. selling a physical item). She sends the change back to herself.
- Alice is moving some specific amount of bitcoin (e.g. 0.1 BTC) from a hot wallet into cold storage and uses the change to buy some 'credits' at Bob's company.
- Alice is moving some specific amount of bitcoin (e.g. 0.1 BTC) from a hot wallet into cold storage and uses the change to donate to Bob.

Scenario B -  Alice sends to Bob in two outputs

Example Scenarios:
- Alice is paying Bob for a product (of fixed BTC amount) and uses the change to buy some 'credits' at Bob's company.
- Alice is paying Bob into two addresses at Bob's request. Perhaps one is Bob's cold storage and the other is Bob's hot wallet.

## Assuming Three Parties:

| IN_1    | OUT_1   | OUT_2   |
| ------- | ------- | ------- |
| Alice   | Bob     | Charlie |

Alice sends some to Bob, and some to Charlie.

Example Scenarios:
- Alice is paying Bob for a product (of fixed BTC amount) and uses the change to buy some 'credits' at Charlie's company.
- Alice is paying Bob for a product (of fixed BTC amount) and uses the change to donate to Charlie.

## 1 IN | 2 OUT Suggestions

There are four ways to interpret this basic transaction.
The most common is likely a two party, type A transaction, given that it is common for the receiver to specify the amount to be sent.

In addition to the suggestions in the previous section
- Users could send to themselves with two outputs to increase the number of this type of transaction (may increase tx fees later.)
- Receivers could ask to be paid into two addresses to increase the number of this type of transaction (may increase tx fees later.)
- Encourage users to make donations by sending the change in a transaction they would otherwise make (rather than as a separate transaction).

# Conclusion

In conclusion there are the following actionable suggestions;
- Raise awareness of the (trustworthy) services that have 'credit' accounts
- Encourage more (trustworthy) services to allow this type of 'credit' arrangement
- Invent alternate methods of paying with a full coin (change back on in a batched transaction or over lightning?)
- Encourage users who trust each other to swap coins (and pay the difference via a side channel e.g. lightning)
- Users could send to themselves with two outputs to increase the number of this type of transaction (may increase tx fees later.)
- Receivers could ask to be paid into two addresses to increase the number of this type of transaction (may increase tx fees later.)
- Encourage users to make donations by sending the change in a transaction they would otherwise make (rather than as a separate transaction).

Thank you for reading.
I would greatly appreciate any suggestions of other example Scenarios or suggestions. [Message me](https://keybase.io/6102).

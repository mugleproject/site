---
layout: page
---

# Open Research Problems

This document summarizes several open research problems related to Mugle.
Feel free to join us on [Keybase](https://keybase.io/team/muglecoin) to discuss them. Funding available.

## Table of Contents

| Number | Name |
| --- | --- |
| 1 | [BLS Signatures](#1-bls-signatures) |
| 2 | [Accumulator](#2-accumulator) |
| 3 | [Research on ZKPs Recent Advances](#3-research-on-zkps-recent-advances) |
| 4 | [Scriptless Scripts](#4-scriptless-scripts) |
| 5 | [FlyClient](#5-flyclient) |
| 6 | [Asynchronous Transaction Building](#6-asynchronous-transaction-building) |
| 7 | [Reducing Linkability of Outputs On Chain](#7-reducing-linkability-of-outputs-on-chain) |
| 8 | [Erlay Transaction Relaying](#8-erlay-transaction-relaying) |
| 9 | [Payment Channel Hubs](#9-payment-channel-hubs) |

## 1. BLS Signatures

### Description

Introduced in 2001 by Boneh, Lynn and Shacham, BLS signatures introduces non-interactive kernel aggregation and potentially simpler multisignature schemes.

While it is not for certain that such signatures are well suited for Mugle it is still interesting to explore this design.

### Relevant Papers

- D. Boneh, B. Lynn, and H. Shacham. Short signatures from the weil pairing. In Proceedings of the 7th International Conference on the Theory and Application of Cryptology and Information Security: Advances in Cryptology, ASIACRYPT &#39;01, pages 514–532, Berlin, Heidelberg, 2001. Springer-Verlag.
[https://www.iacr.org/archive/asiacrypt2001/22480516.pdf](https://www.iacr.org/archive/asiacrypt2001/22480516.pdf)

- D. Boneh, M. Drijvers, and G. Neven. Compact multi-signatures for smaller blockchains. Cryptology ePrint Archive, Report 2018/483, 2018.
[https://eprint.iacr.org/2018/483](https://eprint.iacr.org/2018/483)

### Other resources

- [BLS Signatures for Busy People](https://gist.github.com/hermanjunge/3308fbd3627033fc8d8ca0dd50809844)

### Github Issue

- [https://github.com/mugleproject/mugle/issues/2504](https://github.com/mugleproject/mugle/issues/2504)

## 2. Accumulator

### Description

In Mugle, kernels, outputs and range proofs are stored in a type of accumulator called a [Merkle Mountain Range](https://github.com/opentimestamps/opentimestamps-server/blob/master/doc/merkle-mountain-range.md). While efficient, there have been several improvements to this kind of data structure, for example RSA Accumulators.
The goal of this research problem is to identify whether or not Mugle can leverage more advanced or faster cryptographic accumulators.

### Relevant Papers

- D. Boneh, B. Bünz, and B. Fisch. Batching techniques for accumulators with applications to IOPs and stateless blockchains. Cryptology ePrint Archive. 2018
[https://eprint.iacr.org/2018/1188.pdf](https://eprint.iacr.org/2018/1188.pdf)


## 3. Research on ZKPs Recent Advances

This research subject is about investigating recent advances in zero knowledge proofs and how Mugle can leverage their potential improvements. Improvements can be on:
- Alternative small proof of existence of kernel history up to horizon
- Privacy
- Soundness
- Hardness
- Efficiency (whether speed or size)
- ...

### Relevant papers
 - https://eprint.iacr.org/2020/1618.pdf - Proof-Carrying Data without Succinct Arguments
 - https://eprint.iacr.org/2019/1021.pdf - Halo: Recursive Proof Composition without a Trusted Setup
 - https://www.benthamsgaze.org/2019/02/07/introducing-sonic-a-practical-zk-snark-with-a-nearly-trustless-setup/ - SuperSonic
- https://github.com/matter-labs/awesome-zero-knowledge-proofs - Awesome Zero Knowledge Proofs

## 4. Scriptless Scripts

### Description

Mimblewimble does not support any kind of script. In 2017, Andrew Poelstra introduced a way to add smart contract ability to this type of blockchain: scriptless scripts.

While a significant research effort has been done on the subject there are very few concrete implementations of such cryptographic structure.

The goal of this research problems is to investigate scriptless scripts in Mugle and potentially implement basic contract features.

### Relevant Presentations

- [Scriptless Scripts by Andrew Poelstra](https://download.wpsoftware.net/bitcoin/wizardry/mw-slides/2017-03-mit-bitcoin-expo/slides.pdf) (2017)
- [Scriptless Scripts with Mimblewimble (Muglecon US)](https://www.youtube.com/watch?v=EN-JMlzr8Qw&index=7&list=PLvgCPbagiHgqOe0z_xgrIsGq-ayVZcNjy)

## 5. FlyClient

### Description

&quot;To validate transactions, cryptocurrencies such as Bitcoin and Ethereum require nodes to verify that a blockchain is valid. This entails downloading and verifying all blocks, taking hours and requiring gigabytes of bandwidth and storage. Hence, clients with limited resources cannot verify transactions independently without trusting full nodes.[...] FlyClient is a novel transaction verification light client for chains of variable difficulty. FlyClient is efficient both asymptotically and practically and requires downloading only a logarithmic number of block headers while storing only a single block header between executions.&quot;

The goal of this research problems is to investigate/implement the necessaries prerequisites for the introduction of FlyClient in Mugle.

### Relevant Papers

- B. Bünz, L. Kiffer, L. Luu, and M. Zamani. Flyclient: Super-light clients for cryptocurrencies. IACR Cryptology ePrint Archive, 2019:226, 2019.
[https://eprint.iacr.org/2019/226.pdf](https://eprint.iacr.org/2019/226.pdf)

### Github Issue

- [#1555](https://github.com/mugleproject/mugle/issues/1555)

## 6. Asynchronous transaction building

### Description

One of the trade-offs of the Mimblewimble type blockchain is that it requires a round trip between the payer and payee to construct a valid transaction. Meaning that the sender and receiver must be online to transact.

Several research attempts have been made in that direction. For example, relying on [federated relays](https://muglebox.io) or [Beam shared bulletin board system](https://medium.com/beam-mw/the-secure-bulletin-board-system-sbbs-implementation-in-beam-a01b91c0e919).

The goal is this research problem is to investigate and develop an asynchronous, robust, and privacy preserving method of building Mugle transactions.

### Github Resources

- [Mugle Draft RFC - Asynchronous Transacting via Relays](https://github.com/DavidBurkett/mugle-rfcs/blob/offline-transacting/text/0000-asynchronous-transacting-via-relays.md)

## 7. Reducing Linkability of Outputs On Chain

### Description

Mimblewimble/Mugle leverage [confidential transactions](https://en.bitcoin.it/wiki/Confidential_transactions) to hide the identity of the sender and recipients. As such, there are no public amounts or addresses.

However, it is possible for someone listening on the network to build a transaction graph and possibly clustering entities together.

Techniques like [Dandelion++](https://arxiv.org/abs/1805.11060) mitigate this issue but are insufficient for a privacy coin.

A much more promising design is this Mimblewimble [CoinSwap proposal](https://forum.mugle.org/t/mimblewimble-coinswap-proposal)

The goal of this research is to investigate ways to obfuscate the Mugle transaction and implement such design.

### Relevant Papers

- Ian Miers - Blockchain Privacy: Equal Parts Theory and Practice (especially Flashlight Attack part)
https://www.zfnd.org/blog/blockchain-privacy/#flashlight

## 8. Erlay Transaction Relaying

Erlay is a transaction dissemination protocol proposed by G. Naumenko, G. Maxwell, P. Wuille. The motivation is to improve connectivity between Bitcoin nodes and reduce the bandwidth required to operate a full node. It claims to reduce the bandwidth consumption by 40% assuming current connectivity, and keeps bandwidth use almost constant as connectivity increases. It also hardens the network against attacks that attempt to learn the origin node of a transaction.

This protocol could prove useful to Mugle as well, and it is of value to the community to investigate how this best should be implemented.

### Relevant Papers
https://arxiv.org/pdf/1905.10518.pdf

### Github issue
https://github.com/mugleproject/mugle/issues/2857

### Forum thread
https://forum.mugle.org/t/erlay-bandwidth-efficient-transaction-relay-in-bitcoin/5081

## 9. Payment Channel Hubs

Payment channel hubs offer the possibility of instant payments that improve privacy by joining transactions (like a coinjoin server), and improving scalability by pruning intermediate txs and potentially even aggregating kernels. Mugle already has NRD (NoRecentDuplicate) kernels waiting to be activated, which provide the relative timelocks needed for implementing basic payment channels. The difficulty is in trying to design a PCH that is trustless (can't steal/freeze coins or rollback txs), and that doesn't learn everything about the individual transactions (amounts, input/output links, etc). These past few years have seen a lot of developments in this area (TumbleBit, Bolt, A2L, etc.) but nothing that can be directly applied to Mugle in a way that doesn't requiring trusting hub operators to preserve your privacy.

### Relevant papers
 - https://eprint.iacr.org/2016/701 - Bolt
 - https://eprint.iacr.org/2016/575 - TumbleBit
 - https://eprint.iacr.org/2019/589 - Anonymous Atomic Locks (A2L)

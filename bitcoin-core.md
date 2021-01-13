# Bitcoin Core client

[Bitcoin Core](https://bitcoincore.org) is the dominant software client of the Bitcoin network, currently making up ~90% or more of the network nodes (see https://bitnodes.io/nodes).

Version 0.1 was released by Satoshi Nakamoto on January 9th, 2009. Initially it was released under the “Bitcoin” name. Later, when several clones of Bitcoin appeared (e.g. BitcoinCash, BitcoinABC), the software project was renamed to “Bitcoin Core” to distinguish it from other networks. Contributors to the Bitcoin project also became known as “Core developers”. The project has an active [mailing list](https://lists.linuxfoundation.org/mailman/listinfo/bitcoin-dev) and an [IRC channel](https://bitcoincore.org/en/meetings). 

Bitcoin Core software is very unique in several aspects:

* Core is **Peer-to-Peer** (P2P). There are no central servers. Every Core node, when booted up for the first time, will attempt to sync the entire history of the blockchain from its peers, which might take a few hours, even days. A “full node” is a node that fully validates transactions and blocks and has an entire copy of the blockchain. The reason for this architecture is to minimize trust and is crucial to Bitcoin’s security model: “do not trust, verify”. A Core node makes little trust assumptions on its peers, and if it finds that its peers are serving conflicting versions of the blockchain, it will accept the one that has the most Proof-of-Work behind it.

* Core can be considered the “**unofficial spec**” of the Bitcoin network. Newer features of Bitcoin do have specs, called Bitcoin Improvement Proposals, or BIPs (see the full list of BIPs [here](https://github.com/bitcoin/bips)). But much of Bitcoin code still has no spec. If there are multiple Bitcoin clients running without an official spec, they may disagree on what transactions and blocks are valid (a.k.a. the “consensus” layer of Bitcoin). This might cause nodes to fall out of consensus and split the blockchain into two or more branches. In order to avoid this, most developers agree that (a) having multiple clients of Bitcoin is generally not a good idea and (b) the code of the dominant Bitcoin client, Core, should be the de facto standard. This extends to even things like bugs!

* Core **must be 100% backward-compatible**. New releases of Core must be fully backward-compatible with older releases, in order to avoid consensus errors. This requirement must go back to the very first version of Core. Nothing in the software world has as stringent a requirement on backward-compatibility as Bitcoin Core!

In practice, the consensus part of the Bitcoin code matters the most. Peripheral components of Bitcoin client software such as P2P networking code or the wallet code have laxer requirements. They can have different implementations, or are not as strict when it comes to maintaining backward-compatibility.

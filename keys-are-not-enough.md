<h1>"Not Your Keys, Not Your Coins"... Is Not Enough</h1>

This slogan (perhaps coined by Bitcoin evangelist Andreas Antonopoulos) has been popular among the Bitcoin community for a long time. "Keys" here refer to the private keys, implying that those who are in possession of the private keys, own the bitcoins controlled by those keys.

While this slogan was true in the early days of Bitcoin, it is becoming increasingly irrelevant. The reason is the introduction and growing adoption of more advanced smart contracts, including, but not limited to, multisig.

Since Nunchuk's mission is the proliferation of multisig, it is crucial that the first step is to clear up this misconception. The rest of this article explains why the above slogan no longer suffices.

<h2>Back to basics: Bitcoin addresses</h2>

Bitcoin addresses are constructed using 2 components: a data component, and a script component that explains how those data should be used in locking up the bitcoins.

In the early days of Bitcoin, both the data component and the script component were incredibly simple. The data is usually one single public key in uncompressed form. The script component is similarly straightforward. It either involves a single operation, OP_CHECKSIG (P2PK), or a slightly longer list of operations (P2PKH), but still highly predictable. In those days, the addresses act ultimately as aliases for the public keys. They are practically one and the same.

In this context, the aforementioned slogan makes sense. Whoever posseses the private keys, can deduce the public keys. And from the public keys, the addresses. So possession of the private keys means that:
* You know which addresses your bitcoins are stored in, and 
* How to unlock the bitcoins, once you know the addresses.

<h2>BIP16/BIP32</h2>

Things started to change with the introduction of more advanced scripting capabilities, beginning with [BIP16 (P2SH)](https://github.com/bitcoin/bips/blob/master/bip-0016.mediawiki). With P2SH, the script component can be almost anything. A good example is [Peter Todd's bounties](https://bitcointalk.org/index.php?topic=293382.0) for finding cryptographic hash collisions. But a more typical use case for P2SH invloves multisig wallets, where funds are controlled by more than one public key.

P2SH-enabled multisig means that addresses are no longer predictable, because the order of the public keys included matters. For example, a 2-of-3 P2SH multisig address could be built 6 different ways, depending on how you order the 3 public keys. If you don't back up the redeemScript, which contains this order, you might not even know which addresses belong to you! All is not lost, since you can "try out" all permutations. But this brute-force approach is problematic, as we shall see later on.

Another development occured on the key component side of the address. Some time after P2SH was created, Hierarchical Deterministic (HD) wallets arrived. HD wallets were later standardized in [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki). Prior to HD wallets, a wallet is simply a collection of random private keys, the keys baring no relationship to one another. HD wallets mean that the private keys belong to the same family, all generated from the same root, called the master key.

HD wallets also make addresses less predictable. Since now the user primarily deals with the master key, for each address, you need to know from which lineage the public key descended from the master key. This is called BIP32 derivation path. Without knowing the derivation path, you would also not be able to tell which addresses on the blockchain belongs to you.

To sum up: the introduction of BIP16 and BIP32 meant that possession of the private keys no longer suffices. You also need the redeemScript (for BIP16) and derivation path (for BIP32).

<h2>SegWit and Taproot</h2>

Things became even more complicated with the activation of [Segregated Witness](https://en.bitcoin.it/wiki/Segregated_Witness), a much-anticipated suite of protocol updates that fix critical issues such as transaction malleability.

SegWit introduced a new and improved address format, called Bech32.

The problem is that now there are even more ways addresses can be generated from a single master key. For each address type (there are now 3: legacy, native segwit, and a hybrid called nested segwit), you face the same problems of BIP16 and BIP32. So you have permutations upon permutations of address possibilities!

Levels of permutations:
1. Address types
2. Script types
3. Derivation paths
4. Order of keys, if multisig

This is where we are today. Both the key component and the script component of the address have gotten highly complex that possession of private keys makes up only a small part of ownership.

During this period, wallet providers coped with this complexity through their own ways, often ad-hoc and non-standard, which led to unfortunate consequences. First, wallets became less compatible with one another. As an example, to recover a wallet created with one provider in another provider requires looking up magic "recovery paths". Another negative side effect is the invention of poor concepts such as YPUB/ZPUB that further complicates the process and confuses the user. We will discuss YPUB/ZPUB and why they should be avoided separately in another article.

But it doesn't stop here. Soon Bitcoin will have even more advanced scripting capabilities, such as [Taproot](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki). When that happens, the number of address permutations increases even further.

<h2>Solution: Descriptor Language</h2>

Perhaps realizing the urgency of this problem, Core developer Pieter Wuille set out to solve it. Pieter realized what we ultimately lacked was a higher-level language to tame this monstrous complexity. His solution, the [Output Descriptor language](https://github.com/bitcoin/bitcoin/blob/master/doc/descriptors.md) (descriptor for short) , elegantly solves this problem.

The purpose of the descriptor language is to express how keys are derived and how precisely they are used in creating  addresses.

With descriptors, the user only needs to back up 2 things for their wallet: the master keys (or BIP39 seeds), and the descriptors. There would no longer be any ambiguity, either in knowing which addresses on the blockchain belong to you, or how to recover the wallet using third-party tools.

The days of "not your keys, not your coins" are over. Perhaps it is more fitting now to say:

"Not your keys, not your descriptors, not your coins".

===

*Nunchuk (Engineering) Journal is a collection of articles that discuss all things technical in Bitcoin. The journal documents our thought processes in the creation of Nunchuk, how things impact the user, and observations about the industry at large.*


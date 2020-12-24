# Bitcoin 101 Series: The Anatomy of Proof-of-Work

Proof-of-Work (PoW) was originally invented as a [measure against email
spams](https://en.m.wikipedia.org/wiki/Proof-of-work_system). Only later it was
adapted to be used in digital cash [1].

What PoW mining actually does under the hood, is that it converts kinetic energy
(electricity) into a ledger block. A mining machine repeatedly performs hash
operations until it solves a cryptographic puzzle. All hash operations are
thrown away except for the one hash that solves it.

This one tiny hash, which itself takes very little energy to compute, is a
direct representation of the huge ball of energy that was required to produce
it. The “proof” that the block was minted. In order to rewrite the block, an
attacker later will have to spend a roughly equivalent number of hash operations
that was originally required.

Let’s say that again: reverting takes an equivalent number of hash operations,
not an equivalent amount of energy. That is because the hash is only a
representation of the energy used, not the energy itself.

Over time, this representation of energy becomes less and less accurate — as
improved hardware becomes more efficient. Energy itself doesn’t change, but its
old representations “leak”.

Another way to visualize this process, is to think of PoW mining as attaching
physical weights to virtual blocks. Over time the older blocks get damaged and
get lighter and lighter. This also reduces the total weight of the chain, all else
being equal.

Bitcoin combats this attrition process by constantly creating new blocks with
fresh weights. This ensures that the tip of the chain is always heavy in the
present, protecting the integrity of the entire chain. Heavy chain == secure
chain.

(Some have suggested that “heaviest chain” is a better terminology than
Satoshi’s “longest chain.” Longest chain can be very misleading when we don’t
really mean length in the literal sense.)

SHA256 is the hash function that backs Bitcoin PoW mining. SHA256 protects the
ledger from being rewritten. One hash in (to mine), one hash out (to revert).
This is what gives Bitcoin its immutability property [2].

It’s amazing when you think about it. Hash operations dedicate their entire
existence to the purpose of securing the ledger! Rarely anything in the real
world has 100% dedication and efficiency. (e.g.: contrast that with gasoline and the
combustion engine).

In reality, it is probably not 100% but something close to it. Because
irreversibility relies on the hashed results being uniformly random (just like
when you roll a fair dice), and algorithms can’t truly simulate real-world
randomness.

Luckily for us, hash functions such as SHA256 have shown to be [sufficiently
random](https://www.eecs.harvard.edu/~michaelm/postscripts/soda2008b.pdf), aka
“pseudorandom”. SHA256 has been reviewed and stress-tested for years, and has a
rich research literature behind it. So it’s not something we have to be too
concerned about (yet).

Fundamentally, I believe the idea of “attaching energy” to blocks is the right
one and probably the only way to simulate immutability virtually.

**Using energy burnt to back a block allows us to view immutability objectively.
Whereas any non-energy-based method ultimately requires someone’s **[subjective
interpretation of
immutability](https://twitter.com/hugohanoi/status/953346280134029312)**.** [3]

By attaching energy to a block, we give it “form”, allowing it to have real
weight and consequences in the physical world. We can also think of PoW as the
magic that brings a bunch of 0s and 1s into life.

In other words, **PoW is the bridge between the digital and the physical**.

Compare that to some cryptokitties that someone creates, modifies and removes as
they see fit. Their uniqueness and existence are neither guaranteed nor reliable.

Even if the current variant of PoW fails, I’m confident that there will be other
ways of attaching energy to a block.

In conclusion, PoW’s application in blockchains might prove to be far more
significant and wide reaching than what it was originally invented for. PoW gives
us immutability, which gives us uncensorable money, which could potentially
change how society organizes itself. (Read Nick Szabo’s wonderful essay on
[social
scalability](https://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html)
for more on that.)

*Original article [here](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667).*

*[1]: The idea of using PoW in digital cash might have originated from Wei Dai’s
b-money and Nick Szabo’s bitgold proposals in the late 90’s. Hal Finney created
the first implementation of PoW in digital cash (RPOW) in 2004.*

*[2]: Immutability is a relative concept. When we say ‘immutability’ we usually
mean it’s practically immutable, not absolutely immutable. Even Gold can be
synthesized given enough energy.*

*[3]: One such method is Proof-of-Stake. Read *[this](https://medium.com/@hugonguyen/proof-of-stake-the-wrong-engineering-mindset-15e641ab65a2)*
to understand its pitfalls and why it might be inferior to Proof-of-Work.*

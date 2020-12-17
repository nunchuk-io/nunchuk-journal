### Bitcoin 101 Series: The Origin of Bitcoin

Bitcoin has a spiritual origin and a technological origin. Satoshi also added
his own inventions to complete the system.

*****

### Spiritual Origin (1/2 story)

For full context, read:
[https://www.coindesk.com/the-rise-of-the-cypherpunks](https://www.coindesk.com/the-rise-of-the-cypherpunks).

From after WW2 to early 1990s, governments have a monopoly on cryptographic
techniques such as public-key cryptography. In the US, cryptography was listed
under “munitions list” (weapons) and severely restricted by laws.

The “cypherpunks”, seeing governments’ control of this technology as unjust,
sought to regain the balance. They believe that Privacy is a fundamental human
right, and people should be free to use encryption for their communication.

> **We cannot expect governments, corporations, or other large, faceless
> organizations to grant us privacy out of their beneficence.** It is to their
advantage to speak of us, and we should expect that they will speak. To try to
prevent their speech is to fight against the realities of information.
Information does not just want to be free, it longs to be free.

> We must defend our own privacy if we expect to have any. We must come together
> and create systems, which allow anonymous transactions to take place. People
have been defending their own privacy for centuries with whispers, darkness,
envelopes, closed doors, secret handshakes, and couriers. The technologies of
the past did not allow for strong privacy, but electronic technologies do.

> We the Cypherpunks are dedicated to building anonymous systems. **We are
> defending our privacy with cryptography, with anonymous mail forwarding systems,
with digital signatures, and with electronic money.”**

> **Cypherpunks write code.** We know that someone has to write software to defend
> privacy, and since we can’t get privacy unless we all do, we’re going to write
it. We publish our code so that our fellow Cypherpunks may practice and play
with it. Our code is free for all to use, worldwide. We don’t much care if you
don’t approve of the software we write. We know that software can’t be destroyed
and that a widely dispersed system can’t be shut down.” — A Cypherpunk’s
Manifesto, by Eric Hughes (1993)

Bitcoin came out of this cypherpunk movement, after many earlier attempts at
“electronic money”. Most notable were: Digicash (David Chaum), hashcash (Adam
Back), b-money (Wei Dai), bitgold (Nick Szabo). Most of these projects failed or
were never implemented, but they left important hints. 

Whether Satoshi considered himself a cypherpunk was not clear, but Satoshi
acknowledged the above line of technical experimentation and made references to
them in his white paper. His early quotes were also consistent with cypherpunk
ideals:

> “We can win a major battle in the arms race and gain a new territory of freedom
> for several years.” (2008)<br> “Governments are good at cutting off the heads of
a centrally controlled networks like Napster, but pure P2P networks like
Gnutella and Tor seem to be holding their own.” (2008)<br> “The root problem
with conventional currency is all the trust that’s required to make it work. The
central bank must be trusted not to debase the currency, but the history of fiat
currencies is full of breaches of that trust.” (2009)

### Technological Origin (the other 1/2 of the story)

Full context:
[https://queue.acm.org/detail.cfm?id=3136559](https://queue.acm.org/detail.cfm?id=3136559)

On the other hand, many building blocks of Bitcoin actually came from research /
academia (some of them exotic and long forgotten). Examples:

* Public-Key Cryptography: Diffie & Hellman, 1976, Stanford
* Merkle Tree: Ralph Merkle, 1979, Berkeley/Stanford
* Linked timestamping: Haber & Stornetta, 1991–1997, Bellcore research
* Proof-of-Work: Dwork & Naor, 1992, IBM Research; Adam Back, 1997

Notably, Bitcoin elegantly solves the Byzantine Generals Problem, which was
described in the seminal paper by Lamport (1982):
[https://dl.acm.org/doi/10.1145/357172.357176](https://dl.acm.org/doi/10.1145/357172.357176)

Using Proof-of-Work and under an open, permission-less system (nodes can come
and go as they like), Bitcoin can achieve consensus as long as 51% of the
network mining power is honest.

(However, Satoshi did not reference Lamport’s in his white paper).

### The genius of Satoshi

Building on achievements by earlier cypherpunks and academic researchers,
Satoshi’s contributions came mainly in 3 areas:

* Combine all the basic building blocks into a complete system.
* Invented **Difficulty Adjustment Algorithm** (DAA), to deal with changing
hardware and volatile market demand.
* **Embedded incentives** into the network to ensure it is sustainable, despite
being decentralized and trust-minimized.


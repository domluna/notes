Stellar Consensus
=================

SCP -> Stellar Consensus Protocol

SCP achieves all 4 consensus mechanisms

1. decentralized control
2. low latency
3. flexible trust
4. asympotic security


Federated byzantine agreement, or FBAS, is a pair (V, Q) comprising a set of nodes V
and a quorum function Q: V -> 2^(2^V) - empty set

Uses no game-theoritic ideas. So a big takeaway here is that mining is not required, therefore, neither is the 10 min waiting period to solve the puzzle.

So it builds byzantine agreement ideas, where 2,3,4 of the upon list are secured. Quorum slices allow for the decentralized control. The client can pick who they trust, they still have to trust someone but they can chose whom. Each node chooses its own quorum slice.

How the quorum slices are chosen is therefore VERY important. We want quorum intersection. Quorum intersection is where nodes in quorum slices overlap.

The converse of this, quorum disjoint can block consensus. If quorum slice A and B are quorum disjoint it means they might come to different agreements.



10 minutes transactions
-----------------------

It's known the ~10 mins is required for a transaction to be
confirmed and written into the ledger.

This can get in the way of services where transactions need to be
fast (order of seconds). A solution proposed in [1] is to for the mechant
to use N nodes to propogate the transaction to. N << total number of bitcoin
nodes.

Note the initial valid transactions *Tv* has a head start over *Ta*, the attacker
transaction. Even just a second makes a huge difference due to the exponential 
propagation.

In order for the attacker to succeed they have to meet two conditions:

  a) *Ta* must be confirmed by the bitcoin network
  b) *Ta* must not be seen by the N nodes. The merchant has to think
  *Tv* is has gone through.

The merchant connects to N nodes and listens for a propagation depth(short time). If any
of the N nodes logs *Ta*, the merchant is informed of the double spend. After the propagation
depth the merchant propogates *Tv*.

We can see that it's crucial the attacker propagates *Ta* as soon as possible. However,
during propogation depth, if one of N nodes detects the transaction the gig is up. 
But if the attacker waits too long the transaction will be exponentially behind.

The simulations in [1] showed with N=40 the probability of a successful double
spend is 0.088%.

[1] [Have a Snack, Pay with Bitcoins](http://www.tik.ee.ethz.ch/file/848064fa2e80f88a57aef43d7d5956c6/P2P2013_093.pdf)

Optimization for training deep models
-------------------------------------

Use gradient clipping to deal with large gradient jumps.

[Chapter 8](http://www.iro.umontreal.ca/~bengioy/dlbook/optimization.html)

## Vanishing/Exploding Gradient Problem

Consequence of deep networks is the composition of multiple Jacobian matrices.
This creates derivatives that either vanish (-> 0) or explode (-> +/-Inf).

This is even more of an issue when dealing with highly related Jacobians.

A particular consequence is learning long-term dependencies. When the system
is able to learn long-term dependencies it is also in a situation where gradients
vanish and long-term dependencies have an exponentially smaller weight than short-term
dependencies.

The signal of the long-term dependencies is hidden by the short-term.

## Curriculum Learning

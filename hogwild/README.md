Hogwild!
========

Previous attempt at parallelizing SGD have been unsuccessful due to locking which destroys
any hoped performance gain.

HOGWILD! allows processors to access shared memory and the possibility of overwriting
each other's work. 

When the optimization problem is sparse, meaning most gradients update only modify
small parts of the decision variable. In this case HOGWILD! achieves a nearly optimal rate
of convergence.

## More on Sparsity


## References

[1] Hogwild!: A Lock-Free Approach to Parallelizing Stochastic Gradient Descent
http://www.eecs.berkeley.edu/~brecht/papers/hogwildTR.pdf



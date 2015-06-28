Compressive Sensing
===================

### Goal

Reconstruct a signal from a sparse representation. It's like compression but before
you would do the actual regular compression.

Example: Take a picture with fewer pixels.

### Main Theorem

Fix a signal length *n* and a sparsity level *k*. Let A be an m x n matrix with
m = Theta(k log(n/k)) rows, with each of its m*n entries chosen independently from
the standard Gaussian distribution. With high probability over the choice of A, every k-sparse signal z
can be efficiently recovered from b = Az.

k-sparse meaning it has at most k non-zero entries.



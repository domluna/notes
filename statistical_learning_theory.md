Statistical Learning Theory
===========================

### Data Generation Assumption

All pairs (X,Y) X x Y are drawn i.i.d. from some unknown Probability
dist over X x Y.

Expected loss of a decision function f: X -> A

is  L(f) = E l(f(X), Y)

f cannot be directly computed since we don't know the expectation
of the distribution.

f*: X -> A is the function which achieves minimal risk over
all possible functions.

### Observations

1. The more data we have the better, we can better estimate the underlying
distribution.

2. If data is scarce, we need to efficient ways to generate/sample data. Not
only must it be efficient but it must capture the underlying distribution. If
this is not the case we can easily suffer from too much bias or variance.

3. Need an optimization method to find f*

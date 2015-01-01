Generative vs. Discriminative
-----------------------------

Discriminative is where we try to calculate p(C\_k | x) directly.

Generative is where we calculate p(C\_k | x) via Bayes' rule.

First calculate p(x | C\_k) then use Bayes' rule together with
p(C\_k) to find the posterior values.

p(C\_k | x) = p(x | C\_k) * p(C\_k) / p(x)

where p(x) = Sum over k: p(x | C\_k) * p(C\_k)

This is called generative because we can use p(x) to generate
artificial input data.

Generative method can train classes independently, while Discriminative
methods have to be retrained each time a new class is added.

This can be seen because p(x | C\_k) and p(C\_k) are based on the k
class itself and not x. Altering p(x) is as easy as adding another class
to the p(x) summation.

Discriminative methods give better results because they focus
all their effort on finding the correct classification boundaries between
classes.

Discriminative methods are what typical neural networks do. We give the input x
as a black box; the model has no idea what the prior p(x) might be, etc.

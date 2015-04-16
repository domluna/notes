IRNN
----

[Paper](http://arxiv.org/pdf/1504.00941v1.pdf)

Initialize RNN matrices to identity(rather than random) and use ReLU vs (Tanh/Logistic)
Biases -> 0

Non-recurrent weights sampled from Gaussian with mean = 0 and sd = 0.001

Scaling the identity by a small constant shows to reduce long-term memory


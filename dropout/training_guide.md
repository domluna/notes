Practical Guide for Training Dropout Networks
=============================================

## Network Size

If an n sized layer is optimal for a standard net on a given task, a good dropout net should n/p units. This is a useful heuristic for setting the number of hidden units in fully connected and convolutional networks.

## Learning Rate and Momentum

Dropout produces significant noise in gradients vs normal SGD. In order to make up for thisa dropout net should use 10-100x the learning rate that was optimal for the standard net.

Another approach to reduce noise is momentum. For standard nets the parameter is 0.9 but for dropout nets values 0.95 - 0.99 work better.

High learning rate and/or momentum significantly speed up learning.

## Max-norm Regularization

Though large momentum and learning rate speed up learning, they sometimes cause the
network weights to grow very large.

Prevent via max-norm regularization. Constrains the norm of the vector of incoming weights at each hidden unit to be bound by a constant c. c typically ranges from 3 - 4 

## Dropout Rate

Droput introduces parameter p, this parameter controls the intensity of the dropout. If p = 1 then it implies no dropout and low values imply high dropout.

p values typically range from 0.5 - 0.8

For real-valued inputs (image patches or speech frames), a typical value is 0.8.

For hidden layers, the choice of p is coupled with the size of hidden units. Smaller p requires bigger n (underfitting). Large p may not produce enough dropout (overfitting).




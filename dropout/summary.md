Summary
=======

Dropout takes 2-3x longer to train than regular nets. Due to noisy parameter updates, effectively training new network each case. Gradients being computed are not gradients of final architecture at test time.

Dropout reduces overfitting.

Standard Backprop builds up brittle co-adaptations that don't generalize well to new data.

Dropout makes the presence of a particular unit unreliable, this leads to co-adaptations breaking.


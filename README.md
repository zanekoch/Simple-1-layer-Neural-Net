# Simple-1-layer-Neural-Net
First try at a simple neural network
Notes

What is sigmoid fxn and what is use in ML?
A = 1/(1+e^-x)
-essentially a logistic function with the S shaped ruce
-it is an option for an activation function
-output will always be in range of (0,1)
-toward either end of the sigmoid function the Y values tend to respond much less to changes in X
  -gradient is small
  -this is bad because it makes it "refuse to learn" at these values
  
 Activation functions in NNs:
  -Y value, out put of weighted sum plus bias, can be anything -inf to +inf
  -neuron doesn't really know the bounds of the value
  -so how do we decide wether neuron should fire or not?
  -add "activation fxn" to check the Y value produced by a neuron and decide wether outside connection should consider htis neuron as fired or not
  -activation fxn A is "activated" if Y>some threshold
  -alternatively A=1 if Y>some threshold, 0 otherwise
A good activation fxn...
  -non-linear
    -so derivative is not constat AKA gradient has relationship with X
    -makes it so if there is an error in prediction the changes that back propogate are not constant and DO depend on X
    -also good bc if each layer is activated by a linear fxn, then the final activation of the last layer is nothing but jsut a linear fxn of the input of the first layer, making is all essentially one layer
      -bad bc it doesn't allow stacking
 

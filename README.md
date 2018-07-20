# Simple-1-layer-Neural-Net
First try at a simple neural network
Notes

WHAT IS A SIGMOID FUNCTION AND WHAT IS ITS USE IN ML?
A = 1/(1+e^-x)
-essentially a logistic function with the S shaped ruce
-it is an option for an activation function
-output will always be in range of (0,1)
-toward either end of the sigmoid function the Y values tend to respond much less to changes in X
  -gradient is small
  -this is bad because it makes it "refuse to learn" at these values
  
  ACTIVATION FUNCTIONS IN NNS:
  -Y value, out put of weighted sum plus bias, can be anything -inf to +inf
  -neuron doesn't really know the bounds of the value
  -so how do we decide wether neuron should fire or not?
  -add "activation fxn" to check the Y value produced by a neuron and decide wether outside connection should consider htis neuron as      fired or not
  -activation fxn A is "activated" if Y>some threshold
  -alternatively A=1 if Y>some threshold, 0 otherwise
CHARECTERISTICS OF A GOOD ACTIVATION FUNCTION:
  -non-linear
    -so derivative is not constat AKA gradient has relationship with X
    -makes it so if there is an error in prediction the changes that back propogate are not constant and DO depend on X
    -also good bc if each layer is activated by a linear fxn, then the final activation of the last layer is nothing but jsut a linear        fxn of the input of the first layer, making is all essentially one layer
      -bad bc it doesn't allow stacking
      
STEPS OF HOW NN WORKS:
-NNs are essential big composite functions
  -each layer can be represented as a single function whose inputs are a weight vector and output of previous layer
-constructer
-forward propogation
  -each nueron:
    -recieves a set of inputs
    -performs a dot product
    -applies activation fxn to this value (output is layer1)
    -then to cumpute output value:
      -computes the dot product of layer1 and the next weight matrix
      -apply activation function again
-GRADIENT DESCENT:
  -want an optimal value for each weight in network where error is smallest
  -starting at a random weight value we want to take a step in direction of minimum error
    -this direction is the opposite of the gradient
  -if we take mini steps down the gradient we will find smallest error
-HOW TO DO GRADIENT DESCENT:
  -purpose of back propogation is to find the partial derivative of the error with respect to each inividual weight in NN
    -repeatedly applying chain rule through all possible path of network
      -this is to find gradient of each weight with respect to the output
        -do this to be able to update the weight incrementally using gradient descent
  -after getting error for output layer (difference between output and expected):
    -compute error for hidden layers going backwards layer by layer
      -error for a neuron in a hidden layer is the sum of the products between the errors of the neurons in the next layer and weights          of the connections to those neurons multiplied by the derivative of the activation function
     -then use those errors of the hidden layer neurons to calculate the variations of the weights as a result of the current input           patten and ideal outputs
        -product of the input neuron output value and error of the output neuron for that connection
     -The sum of all the variations in weights for each input pattern is calculated
   -then the actual weights are changed by adding the accumulated variations in weights multiplied by the learning rate
      
    
 

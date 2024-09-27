
# Activation functions in Neural Networks



An activation function in the context of neural networks is a mathematical function applied to the output of a neuron. The purpose of an activation function is to introduce non-linearity into the model, allowing the network to learn and represent complex patterns in the data. Without non-linearity, a neural network would essentially behave like a linear regression model, regardless of the number of layers it has.

The activation function decides whether a neuron should be activated or not by calculating the weighted sum and further adding bias to it. The purpose of the activation function is to introduce non-linearity into the output of a neuron. 

### Elements of a Neural Network 
**Input Layer:** This layer accepts input features. It provides information from the outside world to the network, no computation is performed at this layer, nodes here just pass on the information(features) to the hidden layer. 

**Hidden Layer:** Nodes of this layer are not exposed to the outer world, they are part of the abstraction provided by any neural network. The hidden layer performs all sorts of computation on the features entered through the input layer and transfers the result to the output layer. 

**Output Layer:** This layer bring up the information learned by the network to the outer world. 

![neuron_connections_quantization](https://github.com/user-attachments/assets/67a268ee-c9f2-44cc-a501-30ce1c0c9f0f)

**z(1) = W(1)X + b(1) a(1)**


Here,


z(1) is the vectorized output of layer 1  
W(1) be the vectorized weights assigned to neurons of hidden layer i.e. w1, w2, w3 and w4  
X be the vectorized input features i.e. i1 and i2b  
b is the vectorized bias assigned to neurons in hidden layer i.e. b1 and b2  
a(1) is the vectorized form of any linear function



After taking a weighted sum of the inputs plus the bias (W₁X₁ + W₂*X₂ + … + Wn*X𝚗+ b), we pass this value to some activation function ⨍, which then gives us the output of the given neuron. In this case, each of the Xᵢ values is the output of a neuron from the previous layer, while Wᵢ is our neuron's weights assigned to each input Xᵢ.


## 1. Sigmoid or Logistic Activation Function

![image](https://github.com/user-attachments/assets/d9e00cd4-c3e1-4323-8af8-2228e9e41ea2)

The Sigmoid Function curve looks like a S-shape.
The main reason why we use sigmoid function is because it exists between (0 to 1). Therefore, it is especially used for models where we have to predict the probability as an output.Since probability of anything exists only between the range of 0 and 1, sigmoid is the right choice.

The function is differentiable.That means, we can find the slope of the sigmoid curve at any two points.

The function is monotonic but function’s derivative is not.

The logistic sigmoid function can cause a neural network to get stuck at the training time.

The softmax function is a more generalized logistic activation function which is used for multiclass classification.

## 2. Tanh or hyperbolic tangent Activation Function

![image](https://github.com/user-attachments/assets/b3a703cc-fee3-4368-8975-6a8da153b745)

tanh is also like logistic sigmoid but better. The range of the tanh function is from (-1 to 1). tanh is also sigmoidal (s - shaped).
The advantage is that the negative inputs will be mapped strongly negative and the zero inputs will be mapped near zero in the tanh graph.

The function is **differentiable.**

The function is **monotonic** while its **derivative is not monotonic.**

The tanh function is mainly used classification between two classes.  

    Both tanh and logistic sigmoid activation functions are used in feed-forward nets.

## 3. ReLU (Rectified Linear Unit) Activation Function

![image](https://github.com/user-attachments/assets/bef14f5e-70e8-4abc-baa0-18da3280ecee)

The ReLU is the most used activation function in the world right now.Since, it is used in almost all the convolutional neural networks or deep learning.
As you can see, the ReLU is half rectified (from bottom). f(z) is zero when z is less than zero and f(z) is equal to z when z is above or equal to zero.

**Range: [ 0 to infinity)**

The function and its derivative **monotonic.**

But the issue is that all the negative values become zero immediately which decreases the ability of the model to fit or train from the data properly. That means any negative input given to the ReLU activation function turns the value into zero immediately in the graph, which in turns affects the resulting graph by not mapping the negative values appropriately.

## 4. Leaky ReLU Activation Function

![image](https://github.com/user-attachments/assets/117a59bc-fb61-43ef-bc50-7b3e06bc1b54)

It is an attempt to solve the dying ReLU problem. The leak helps to increase the range of the ReLU function. Usually, the value of a is 0.01 or so.

Therefore the range of the Leaky ReLU is (-infinity to infinity).

Both Leaky and Randomized ReLU functions are monotonic in nature. Also, their derivatives also monotonic in nature.

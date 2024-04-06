## Image Flattening

Simple **dense neural networks** pass feature vectors into the 0-th (the first) layer of the computational graph represented by the neural network structure as column vectors. This 0-th layer is essentially the same as with single neuron models. In order to feed our images into such a network we must **flatten** the matrix into a column vector.

![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/5e616088-c30a-48fb-b7a7-c28ebcd76ac6)

We can do this for each image matrix that we are considering by calling the ```flatten()``` method together with the ```reshape(784, 1)``` method to insure it is a column vector. Note, that each image matrix is 28 by 28, and so, $784 = 28 \times 28$ is the number of rows in the flattened matrix column vector. The numerical values in the flattened training and testing data matrices vary between 0 and 255. These large differences in possible values can lead to problems when training the weights and the biases of the neural network. A quick and dirty fix will be to scale all data to belong in the interval $(0, 1)$, i.e., divide the entries by the largest possible value; in this case 255. 


### One-Hot code
---
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/fe965fee-5afe-4034-a2e2-e4c995508835)
---

The following code scales our training and testing data, reshapes our images and stores them in new variable names, and one-hot encodes the labels. 


### Building the Network Architecture 
For our purposes, we will build a multilayered **fully connected**, or **dense**, neural network with $L$ layers, $784$ input notes, $L-2$ hidden layers of arbitrary size, and $10$ output nodes. 

<img src="multilayerPerceptron.jpg" alt="Drawing" style="width: 450px;"/>

For our activation function, we will use the sigmoid function:

* Sigmoid Function
$$
\sigma(z) = \frac{1}{1+e^{-z}}.
$$

For our cost function, we will use the Mean Sqaure Error cost:
$$
C(W, b) = \frac{1}{2}\sum_{k=1}^{10}(\hat{y}^{(i)}_k - y^{(i)}_k)^2.
$$

Our goal will be to write a custom Python class implementing our desired structure. However, before doing so, we first sequentually write functions to better understand the process of programming the following:

* Initializing the weights and biases of each layer
* The feedforward phase
* Calculation of the cost function
* Calculation of the gradient
* Iterating stochastic gradient descent

First we will define our sigmoid activation function, its derivative, and the mean squared error for a single instance of training data. Do this by running the following code. 



### Feedforward Phase

For $\ell = 1, \dots, L$, each layer $\ell$ in our network will have two phases, the preactivation phase $$\mathbf{z}^{\ell} = W^{\ell}\mathbf{a}^{\ell-1} + \mathbf{b}^{\ell},$$ and postactivation phase $$\mathbf{a}^{\ell} = \sigma(\mathbf{z}^{\ell}).$$ The preactivation phase consists of a weighted linear combination of postactivation values in the previous layer. The postactivation values consists of passing the preactivation value through an activation function elementwise. Note $\mathbf{a}^0 = \mathbf{x}^{(i)}$, where $\mathbf{x}^{(i)}$ is the current input data into our network. 

We can test our activation functions and matrix dimensions by running the following code which manually implements the feedforward process on a neural network with the given dimensions.

## Backpropogation Phase with Stochastic Gradient Descent 
We are now ready to define a custom Python ```DenseNetwork``` class which initializes the weights and bias for the network, and implements stochastic gradient descent shown below:

1. For each $i = 1, \dots, N$.
2. Feedforward $\mathbf{x}^{(i)}$ into the network. 
3. Compute $\delta^{L} = \nabla_aC\otimes \sigma'(\mathbf{z}^{L})$.
4. For $\ell = L-1, \dots, 1$, compute $\delta^{\ell} = \big ( (\mathbf{w}^{\ell + 1})^{T} \delta^{\ell + 1} \Big )\otimes \sigma'(\mathbf{z}^{\ell})$.
5. For $\ell = L, L-1, \dots, 1$, 

$$
w^{\ell} \leftarrow w^{\ell} - \alpha \delta^{\ell}(\mathbf{a}^{\ell-1})^{T}
$$

$$
b^{\ell} \leftarrow b^{\ell} - \alpha \delta^{\ell}
$$



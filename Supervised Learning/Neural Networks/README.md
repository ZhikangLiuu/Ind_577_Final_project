# Neural Networks

The Multilayer Perceptron (MLP) is a versatile neural network used for various tasks, including image classification. It consists of interconnected layers and is capable of learning complex patterns in data through feedforward and backpropagation processes.


## Algorithm 
MLP is an artificial neural network (ANN) with three main components: input layer, hidden layer(s), and output layer. Neurons in each layer are interconnected with weighted connections.

MLP operates in a feedforward and backpropagation manner:

**Feedforward:** Input data is passed through the network, and each neuron's output is calculated as a weighted sum of inputs, followed by an activation function.

**Backpropagation:** Network error is computed by comparing predictions to actual targets. Weights are then adjusted using gradient descent to minimize this error.

Training continues iteratively until the network converges to make accurate predictions.

MLP is versatile and widely used for various machine learning tasks due to its ability to model complex relationships in data.

### Feedforward :
**1.Initialization:** Begin with the input layer, where each neuron represents a feature of the input data.

**2.Weighted Sum Calculation:** For each neuron in a hidden or output layer, calculate the weighted sum of its inputs. Each input is multiplied by a corresponding weight, and these products are summed up.

**3.Activation Function:** Apply an activation function to the weighted sum obtained in step 2. Common activation functions include sigmoid, ReLU (Rectified Linear Unit), or tanh (hyperbolic tangent).

**4.Passing to the Next Layer:** The result of the activation function becomes the input for the next layer. This process continues through the hidden layers until reaching the output layer.

**5.Output Layer:** In the output layer, the activations represent the network's predictions or final output.

**6.Prediction:** The final output of the network is used for making predictions, such as classifying an image or producing a numerical value.

### Backpropagation :
**1.Initialization:** Begin by initializing the neural network's weights randomly.

**2.Feedforward Pass:** Perform a feedforward pass through the network to make predictions for a given input, following the steps outlined in the feedforward algorithm.

**3.Error Calculation:** Calculate the error or loss between the predicted output and the actual target values. Common loss functions include mean squared error (MSE) for regression and cross-entropy for classification.

**4.Backpropagation:** Start with the output layer and propagate the error backward through the network. This involves calculating the gradients of the loss with respect to the weights and biases in each layer.

**5.Gradient Descent:** Update the weights and biases in the network using gradient descent or a similar optimization algorithm. The goal is to minimize the error by adjusting the weights in the direction that reduces the loss.

**6.Iterative Process:** Repeat steps 2 to 5 for multiple iterations or epochs, allowing the network to learn and refine its weights gradually.

**7.Convergence:** Continue the training until the network converges, meaning the error reaches a minimum or stabilizes at an acceptable level.

**8.Testing and Evaluation:** After training, use the network to make predictions on new, unseen data to evaluate its performance.

Update Strategy:
There are some kinds of updating strategies to use, here we are going to use Stochastic Gradient Descent(SGD).
The updating algorithm goes:
- **Initialization**: Start with an initial set of weights for the neural network randomly or using predefined values.
- **Iterative Process**:
  1. Shuffle the training dataset randomly.
  2. Split the dataset into mini-batches, each containing a subset of the training examples (usually between 1 and a few hundred).
  3. For each mini-batch:
     - **Forward Pass**: Perform a forward pass through the network to make predictions for the mini-batch.
     - **Error Calculation**: Calculate the error or loss between the predicted output and the actual target values for the mini-batch.
     - **Backpropagation**: Propagate the error backward through the network to compute the gradients of the loss with respect to the weights and biases.
     - **Weight Update**: Update the weights and biases in the network using the computed gradients and a learning rate. The formula for weight update is typically:
         
       new_weight = old_weight - learning_rate * gradient
         
     - Repeat steps 1 to 3 for a specified number of epochs or until convergence criteria are met.
- **Convergence**: Continue training until the algorithm converges, which means that the loss decreases to a satisfactory level or stabilizes.
- **Testing and Evaluation**: After training, evaluate the neural network's performance on a separate test dataset to assess its ability to make accurate predictions

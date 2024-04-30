# Linear Regression

## Introduction
linear regression is a model which estimates the linear relationship between a scalar response and one or more explanatory variables (also known as dependent and independent variables).In linear regression, the relationships are modeled using linear predictor functions whose unknown model parameters are estimated from the data. Such models are called linear models.

## Algorithm 
- **Initialization:**

- 
## Application
**1.Customer Segmentation:**


## Advantages and disadvantages

### Advantages
- **Interpretability:**



### Disadvantages
- **Overfitting:**


# Single Neuron Linear Regression Model

Linear regression via a single neuron involves estimating a function \( f:\mathcal{X} \rightarrow \mathcal{Y} \) that maps input features to a continuous output. This model assumes a linear relationship between inputs and outputs. The neuron uses a linear activation function, and the optimization objective is to minimize the mean squared error between predicted and actual outputs.

## Model Description

- **Inputs**: \( x^{(i)} \) (feature measurements)
- **Output**: \( \hat{y}^{(i)} \) (predicted value)
- **Weights and Bias**: \( w_1 \), \( b \)
- **Activation**: \( a = z = w_1 x^{(i)} + b \)
- **Cost Function**:
  \[
  C(\mathbf{w}, b) = \frac{1}{2N} \sum_{i=1}^{N} (\hat{y}^{(i)} - y^{(i)})^2
  \]
- **Gradient Descent Update Rules**:
  \[
  w_1 \leftarrow w_1 - \alpha \frac{\partial C}{\partial w_1}
  \]
  \[
  b \leftarrow b - \alpha \frac{\partial C}{\partial b}
  \]

## Derivatives for Gradient Descent

The partial derivatives of the cost function with respect to the weights and bias are computed using the chain rule:

- **For a single data point**:
  \[
  \frac{\partial C(w_1, b; \mathbf{x}^{(i)}, y^{(i)})}{\partial w_1} = (\hat{y}^{(i)} - y^{(i)})x^{(i)}
  \]
  \[
  \frac{\partial C(w_1, b; \mathbf{x}^{(i)}, y^{(i)})}{\partial b} = (\hat{y}^{(i)} - y^{(i)})
  \]

## Batch Gradient Descent

Batch Gradient Descent computes the gradient over the entire training dataset and updates the weights in one go.

- **Algorithm**:
  1. For each epoch:
  2. Compute the full gradient for all training data.
  3. Update \( w \) and \( b \) using the learning rate \( \alpha \) and the gradients.

## Stochastic Gradient Descent (SGD)

Stochastic Gradient Descent updates weights and biases for each training example, which allows for faster convergence and can handle larger datasets.

- **Algorithm**:
  1. For each epoch:
  2. For each data point \( i \) in training data:
  3. Compute the gradient using just the single data point.
  4. Update \( w \) and \( b \) using the learning rate \( \alpha \).

## Conclusion

This single neuron model demonstrates a fundamental approach to linear regression in machine learning, utilizing gradient descent to minimize the cost function. It highlights the flexibility of neural network concepts, even in simple linear models, and provides a foundational technique for more complex networks.

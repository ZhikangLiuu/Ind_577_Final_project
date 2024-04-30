# Linear Regression

## Introduction
linear regression is a model which estimates the linear relationship between a scalar response and one or more explanatory variables (also known as dependent and independent variables).In linear regression, the relationships are modeled using linear predictor functions whose unknown model parameters are estimated from the data. Such models are called linear models.

## Algorithm 
- **1. Find a loss function:**
$$
C(\mathbf{w}, b) = \frac{1}{2N}\sum_{i=1}^{N}\Big(\hat{y}^{(i)} - y^{(i)}\Big)^2. 
$$
- **2. Minimize loss function by gradient descent:**
  -- do $$
        w_1 \leftarrow w_1 - \alpha \frac{\partial C}{\partial w_1}
        $$
        $$
        b \leftarrow b - \alpha \frac{\partial C}{\partial b}
        $$
    
- **1. Find a loss function:**
- **1. Find a loss function:**
- **1. Find a loss function:**

  
## Application
**1.Customer Segmentation:**


## Advantages and disadvantages

### Advantages
- **Interpretability:**



### Disadvantages
- **Overfitting:**


# Single Neuron Linear Regression Model

Linear regression via a single neuron involves estimating a function \( f:\mathcal{X} \rightarrow \mathcal{Y} \) that maps input features to a continuous output. This model assumes a linear relationship between inputs and outputs. The neuron uses a linear activation function, and the optimization objective is to minimize the mean squared error between predicted and actual outputs.



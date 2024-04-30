# Linear Regression

## Introduction
linear regression is a model which estimates the linear relationship between a scalar response and one or more explanatory variables (also known as dependent and independent variables).In linear regression, the relationships are modeled using linear predictor functions whose unknown model parameters are estimated from the data. 

## Algorithm 
- **1. Find a loss function:**
  
$$
C(\mathbf{w}, b) = \frac{1}{2N}\sum_{i=1}^{N}\Big(\hat{y}^{(i)} - y^{(i)}\Big)^2. 
$$

- **2. Minimize loss function by gradient descent:**

$$
w_1 \leftarrow w_1 - \alpha \frac{\partial C}{\partial w_1}
$$
  
$$
b \leftarrow b - \alpha \frac{\partial C}{\partial b}
$$
    
There are two kinds of Gradient Descent methods：
- **Batch Gradient Descent：**
  Batch Gradient Descent computes the gradient over the entire training dataset and updates the weights in one go.

- **Stochastic Gradient Descent :**
  Stochastic Gradient Descent updates weights and biases for each training example, which allows for faster convergence and can handle larger datasets.
  
  
## Application
- **Predicting Stock Prices:** Forecasting future stock prices based on historical data.
- **Weather Forecasting:** Predicting temperatures, rainfall, and other weather conditions.
- **Risk Assessment:** Determining the risk factors associated with investment portfolios.


## Advantages and disadvantages

### Advantages
- **Simplicity:** Linear regression is straightforward to understand and interpret, making it easier for non-technical stakeholders to grasp the model's predictions.
- **Efficiency:** It is computationally inexpensive, making it a quick tool for predictions, especially with a moderate to a small amount of data.
- **Less Data Requirement:** Linear regression can perform well with a small amount of data, unlike complex models that require large datasets to train effectively.

### Disadvantages
- **Assumption of Linearity:** Linear regression assumes that there is a linear relationship between the input variables and the output variable, which might not always be the case, particularly in real-world scenarios where relationships can be more complex.
- **Prone to Outliers:** Linear regression models are highly sensitive to outlier observations, which can significantly affect the slope of the regression line and, consequently, the predictions.
- **Underfitting:** Due to its simplicity, linear regression is often prone to underfitting, where the model fails to capture the underlying trend of the data adequately, especially if that trend is complex.




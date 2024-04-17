# Gradient Descent

## Introduction
Gradient Descent is a powerful iterative optimization method used to find parameter values that minimize a cost function, making it crucial in various machine learning models. It is generally attributed to Augustin-Louis Cauchy, who first suggested it in 1847 and also Jacques Hadamard independently proposed a similar method in 1907.

The goal of Gradient Descent is to minimize a function and it is often the loss function given by your own optimization.
Giving a convex function, you pick one point to start.Suppose your function is given by $y=f(x)= (x-2)^2+1$, initial 
$x_0$ is 5 and you want to minimize this function.
The idea to minimize this function is to find the gradient for your points and go along the gradient to reduce the value of 
this function. It is like you are on a hill and you have to walk down the slope of the hill to reach the lowest point。

![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/97d31d07-9de5-49d5-8926-cd8e4256a5ff)

There are some steps of this algorithm：
- find the slope of initial point $f'(w) = 2(w - 2)$
- set your arriving point $$w_{n+1} = w_n - \alpha f'(w_n) $$(noting $\alpha$ is setted by yourself)
- compute and get $w_{n+1}$
- repeat untill it reaches your stopping condition

The figure shows this process:
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/1ce0cfa0-307a-4bb4-8cc5-bd0b6e16e76e)

## Algorithm 
Gradient descent regression is a method used to minimize the cost function in regression models, particularly when dealing with large datasets where traditional methods like ordinary least squares would be computationally expensive. Here's an overview of the algorithm:

1. Initialization: The process begins by initializing the regression coefficients (weights) to random values or zeros. This starting point determines the first step the algorithm will take in the cost function landscape.

2. Cost Function: In regression, the cost function is usually the Mean Squared Error (MSE), which calculates the average of the squares of the differences between the predicted and actual values. The goal of gradient descent is to minimize this MSE.
3. Gradient Calculation: The gradient of the cost function with respect to each coefficient is calculated. This gradient is a vector that points in the direction of the steepest ascent of the cost function. Since the goal is to minimize the cost, gradient descent moves in the opposite direction.
4. Updating Coefficients: The weights are updated by subtracting the product of the learning rate (a small, positive number) and the gradient from them. The learning rate determines the size of the steps taken towards the minimum; too small a rate slows down the convergence, while too large a rate can overshoot the minimum.
5. Iteration: Steps 3 and 4 are repeated iteratively. In each iteration, the weights are adjusted slightly in the direction that reduces the cost function, progressively moving towards the minimum.
6. Convergence: The algorithm converges when the cost function stops decreasing significantly, or a predetermined number of iterations is reached.
7. Stochastic and Mini-batch Variants: In standard gradient descent, the gradient is calculated from the entire dataset, which can be computationally heavy. Stochastic Gradient Descent (SGD) mitigates this by calculating the gradient and updating weights using just one data point at a time. Mini-batch gradient descent strikes a balance by using a subset of the data for each update, offering efficiency and stability.

## Application

- Optimization Problems: Gradient descent is widely used in solving optimization problems across various domains, such as engineering, economics, physics, and operations research. It can be applied to minimize or maximize objective functions representing costs, profits, energy consumption, or any other measurable quantity.
  
- Natural Language Processing (NLP): In NLP tasks like language modeling, text generation, and machine translation, gradient descent is utilized to optimize the parameters of models like recurrent neural networks (RNNs), long short-term memory networks (LSTMs), and transformer-based architectures.

- Computer Vision: In computer vision tasks, including image classification, object detection, and image segmentation, gradient descent is employed to optimize the parameters of convolutional neural networks (CNNs) and other deep learning architectures.

- Reinforcement Learning: Gradient descent plays a crucial role in reinforcement learning algorithms, where agents learn to make decisions by interacting with an environment to maximize cumulative rewards. It is used to update the parameters of the policy or value function approximators.

## Advantages and Disadvantages

**Advantages:**

1. **Scalability and Efficiency:** Gradient descent is computationally efficient and scales well with large datasets. This is particularly true for its stochastic and mini-batch variants, which can handle vast amounts of data without requiring the entire dataset to be loaded into memory.
2. **Flexibility:** It can be used for a variety of optimization problems in machine learning, not just linear regression, but also logistic regression, neural networks, and other models that require optimization of a cost function.
3. **Simplicity:** The concept and implementation of gradient descent are relatively straightforward, making it easy to understand and apply.
4. **Applicability to Non-linear Problems:** Gradient descent can optimize non-linear models, which is a significant advantage over traditional optimization methods that may require linear models.

**Disadvantages:**
1. **Sensitivity to Learning Rate:** The choice of the learning rate can significantly impact the algorithm’s performance. A learning rate that’s too high can cause the algorithm to overshoot the minimum, while a rate that's too low can result in a long convergence time.
2. **Risk of Converging to Local Minima:** In non-convex functions, like those often encountered in deep learning, gradient descent can get stuck in local minima, leading to suboptimal solutions.
3. **Feature Scaling Requirement:** Gradient descent requires careful feature scaling for efficient performance. Without scaling, features with large values can disproportionately influence the cost function, leading to longer convergence times.
4. **Sensitivity to Initial Conditions:** The starting point can affect whether gradient descent converges to the global minimum or a local minimum, especially in complex, high-dimensional spaces.
5. **Plateau Problems:** Gradient descent can slow down near plateaus or saddle points, where the gradient is close to zero, which can extend the time taken to reach the global minimum.
6. **Hyperparameter Tuning:** Besides the learning rate, other hyperparameters (like momentum in SGD) require careful tuning, which can be time-consuming and requires a good understanding of the algorithm.


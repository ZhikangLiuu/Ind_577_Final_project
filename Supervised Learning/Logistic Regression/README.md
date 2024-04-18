# Logistic Regression

## Introduction

Welcome to the Gradient Descent - Logistic Regression project! In this Jupyter notebook, we delve into the Gradient Descent optimization algorithm and its application in logistic regression. Logistic regression is a powerful method for binary classification problems, where the goal is to predict the probability of a binary outcome.

## Algorithm Overview

**Gradient Descent Logistic Regression** is a critical algorithm for fitting logistic regression models, primarily used for binary classification tasks. Here's a concise overview of the algorithm:

1. **Model Definition:** We model the probability of an input belonging to the default class (labeled "1") using a logistic function. This function maps input features to a probability value between 0 and 1.

2. **Cost Function:** The cost function used is the binary cross-entropy loss (log loss), which quantifies the error between predicted probabilities and actual labels.

3. **Gradient Descent:** The parameters of the logistic regression model are iteratively updated to minimize the cost function. Gradient descent moves towards the optimal values for the intercept and coefficients.

4. **Partial Derivatives:** The gradients of the cost function with respect to the parameters are calculated to determine the direction and magnitude of updates.

5. **Updating Parameters:** The parameters (intercept and coefficients) are updated using the gradients and a learning rate until convergence.

6. **Prediction:** The trained model can predict binary outcomes for new input data based on the calculated probabilities.

While efficient for binary classification, logistic regression assumes a linear relationship between features and can be sensitive to outliers.

## Implementation

In this project, we apply Gradient Descent Logistic Regression to analyze the "Rolling Stone Top 500 Albums" dataset. The objective is to explore logistic regression's potential in predicting categorical outcomes, such as classifying albums into genres. By leveraging logistic regression, we aim to uncover underlying patterns in album features that influence these outcomes.

### Loading Dataset

We load the dataset, preprocess it, and encode categorical features to prepare it for training.

### Implementing Gradient Descent for Logistic Regression

We implement Gradient Descent Logistic Regression using Python libraries. This includes preprocessing steps, defining the model, fitting it to the training data, and making predictions.

## Model Evaluation

We evaluate the performance of the logistic regression model by calculating accuracy, F1 score, and generating a confusion matrix. These metrics provide insights into the model's ability to classify albums into the desired categories.

### Conclusion

In summary, the logistic regression model demonstrates promising performance in identifying Rock albums. However, it faces challenges in correctly classifying non-Rock albums, leading to lower precision for non-Rock categories. Possible improvements may involve obtaining more balanced data, feature engineering, or experimenting with alternative model architectures and hyperparameters.

Feel free to explore the notebook, experiment with different aspects of logistic regression, and fine-tune the model to achieve better classification results.

Happy exploring and classifying!

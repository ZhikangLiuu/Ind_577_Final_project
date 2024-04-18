# Logistic Regression

## Introduction

Welcome to the Logistic Regression project! In this Jupyter notebook, we delve into the Gradient Descent optimization algorithm and its application in logistic regression. Logistic regression is a powerful method for binary classification problems, where the goal is to predict the probability of a binary outcome.

## Algorithm 

**Gradient Descent Logistic Regression** is a critical algorithm for fitting logistic regression models, primarily used for binary classification tasks. Here's a concise overview of the algorithm:

1. **Model Definition**: We model the probability of a given input belonging to the default class (labeled "1") using a logistic function:

   $$P(Y=1|X) = \frac{1}{1 + e^{-(b_{0} + b_{1}X)}} $$

   where $b_{0} $ is the intercept,  $b_{1}$  is the coefficient for the input feature $X$ , and the output is a probability that lies between 0 and 1.

2. **Cost Function**: The cost function used in logistic regression is the binary cross-entropy loss or log loss, which is:

   $$J(b_{0}, b_{1}) = -\frac{1}{m} \sum_{i=1}^{m} [y^{(i)} \log(P(y^{(i)}|x^{(i)})) + (1-y^{(i)}) \log(1-P(y^{(i)}|x^{(i)}))] $$

   Here, \( m \) is the number of training examples, \( y^{(i)} \) is the actual label, and \( P(y^{(i)}|x^{(i)}) \) is the predicted probability for the \( i \)-th sample.

3. **Gradient Descent**: This process iteratively updates the parameters \( b_0 \) and \( b_1 \) to minimize the cost function using the update rules:

   $$b_0 := b_0 - \alpha \frac{\partial J}{\partial b_0} $$
   $$b_1 := b_1 - \alpha \frac{\partial J}{\partial b_1} $$

   where \( \alpha \) is the learning rate.

4. **Partial Derivatives**: The partial derivatives of the cost function with respect to \( b_0 \) and \( b_1 \) are:

   $$\frac{\partial J}{\partial b_0} = \frac{1}{m} \sum_{i=1}^{m} (P(y^{(i)}|x^{(i)}) - y^{(i)}) $$
   $$\frac{\partial J}{\partial b_1} = \frac{1}{m} \sum_{i=1}^{m} (P(y^{(i)}|x^{(i)}) - y^{(i)}) x^{(i)} $$

5. **Updating the Parameters**: The update rules are applied until convergence, which occurs when changes to \( b_0 \) and \( b_1 \) are negligible.

6. **Prediction**: For new input data, the model predicts the binary outcome based on the probability \( P(Y=1|X) \). If \( P(Y=1|X) \) is greater than 0.5, the predicted class is "1"; otherwise, it is "0".

This algorithm is efficient for binary classification, but it assumes a linear relationship between the log odds and the features and can be sensitive to outliers.

## Application

1.Medical Field: Predicting the likelihood of a patient having a disease based on observed characteristics of the patient (e.g., age, sex, body mass index, etc.).
2.Financial Sector: Assessing the creditworthiness of borrowers by predicting the probability of default based on their financial histories.
3.Marketing: Determining the likelihood that a customer will purchase a product or subscribe to a service, which can help in targeting promotions and advertisements.We evaluate the performance of the logistic regression model by calculating accuracy, F1 score, and generating a confusion matrix. These metrics provide insights into the model's ability to classify albums into the desired categories.
4.Manufacturing: Predicting the probability of failure of equipment or a production process to help in quality control.

## Advantages and Disadvantages
### Advantages:
1.Interpretability: One of the main advantages of logistic regression is its simplicity and interpretability. The output (odds ratio) can be easily understood and explained

2.Efficiency: Logistic regression is computationally inexpensive to run, making it a good choice for situations where computational resources are limited.

3.Performance: When the underlying relationships are close to linear, logistic regression performs well with fewer assumptions than other algorithms.

4.Probabilistic Prediction: Logistic regression provides probabilities for outcomes, which is informative for decision-making.

### Disadvantages:
1.Assumption of Linearity: Logistic regression assumes a linear relationship between the independent variables and the logit of the dependent variable, which is not always the case.

2.Performance on Large Feature Sets: It can perform poorly if there are large numbers of correlated features, leading to overfitting unless regularization techniques are applied.

3.Multiclass Classification: Logistic regression is naturally suited for binary classification and needs to be adapted for multiclass problems using strategies like one-vs-rest (OvR).

4.Dependence on Entire Data: Logistic regression models are estimated using the entire data set for training, which can make it inefficient in handling huge datasets without sampling or other techniques.

### Conclusion

In summary, the logistic regression model demonstrates promising performance in identifying Rock albums. However, it faces challenges in correctly classifying non-Rock albums, leading to lower precision for non-Rock categories. Possible improvements may involve obtaining more balanced data, feature engineering, or experimenting with alternative model architectures and hyperparameters.

Feel free to explore the notebook, experiment with different aspects of logistic regression, and fine-tune the model to achieve better classification results.

Happy exploring and classifying!

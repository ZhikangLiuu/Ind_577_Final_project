# The Single Neuron Linear Regression Model

In this notebook we implement the single neuron model together with the gradient descent algorithm in order to solve the **linear regression problem**. For teaching purposes, this notebook will focus on single variable regression for a single species of flower in the readily available iris dataset.  

## Regression
Let $\mathcal{X}$ be the space of all possible feature vectors, let $\mathcal{Y}$ be the space of all possible corresponding labels for the feature vectors, and let $f:\mathcal{X} \rightarrow \mathcal{Y}$ be the optimal target function assigning labels to feature vectors in $\mathcal{Y}$. Next recall that in supervised machine learning we observe some subset of features and labels as shown in the figure below. 


In [regression](https://favtutor.com/blogs/types-of-regression), machine learning models are given labeled data $\mathcal{D} = \{(\mathbf{x}^1, y^1), \dots, (\mathbf{x}^N, y^N)\}$, where the feature vectors satisfy $\mathbf{x}^{(i)} \in \mathbb{R}$ and the target labels satify $y^{(i)} \in \mathbb{R}$. Thus, this supervised learning task seeks to predict real valued target labels. This is different from classification (such as the perceptron single neuron model) as the following figure suggests.

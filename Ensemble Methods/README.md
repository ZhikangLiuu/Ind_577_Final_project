# Lecture 9.1 Ensemble Methods

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RandyRDavila/Data_Science_and_Machine_Learning_Spring_2022/blob/main/Lecture_9/Lecture_9_1.ipynb)

**Ensemble methods** are machine learning methods that aggregate the predictions of a group of base learners in order to form a single learning model. For example, imagine that each person in this [video](https://www.youtube.com/watch?v=iOucwX7Z1HU&t=203s) is a trained machine learning model and notice the average of their predictions is a much more accurate prediction that the individual predictions. In this lecture we will consider three types of ensemble concepts and methods. Namely, 
1. **Hard Voting**

2. **Bagging**

3. **Random Forests**

In the rest of this notebook we explore these concepts. 


The term **bagging** referes to **b**ootstrap **agg**regating. **Bootstrapping** is a method of inferring results for a population from results found on a collection of smaller random samples of that population, using replacement during the sampling process. In the context of machine learning, a given set of machine learning model is trained respectively on random samples of training data with replacement (see the above figure), then the combined predictions of each model is **aggregated** and used as a single prediction. For regression tasks this would mean taking the average of the set of model prediction, and for classification taking the majority vote.  

Generally speaking, the models we pick for ensembling will be "dumb learners", meaning models that are barely superior to randomly guessing. Individually the models will perform poorly, but collectively will perform well. 

But why is bagging useful? According to this [article](https://towardsdatascience.com/random-forests-algorithm-explained-with-a-real-life-example-and-some-python-code-affbfa5a942c):

> "Each model is trained on a different dataset, because they’re bootstrapped. So inevitably, each model will make different mistakes, and have a distinct error and variance. Both the error and variance get reduced in the aggregation step where, literally in the case of Regression, they are averaged out."

The key idea here is the reduction in variance of the model. Again, from the above article:

> "In a Regression task you can calculate actual variance of the prediction compared to the true targets. If the tree produces results that are too far off from its true targets, it has high-variance and therefore, it is overfit."

To illustrate this concept we will once again consider the iris dataset; and compare the performance between a single decision tree model and a bagging classifier of many depth 1 decision trees, referred to as *decision stumps*. Run the following code cell to load the iris dataset and visualize the data. 


## Random Forests 
Technically speaking, the above bagging model is called a **Random forest**. Such a model exists inside the ```sklearn.ensemble``` module, and is the ```DecisionTreeClassifier``` class. However, the random forest algorithm used in training the ```RandomForestClassifier``` class introduces extra randomness when growing trees; instead of searching for the best feature when splitting a node, it searches for the best feature among a random subset of features. This results in a greater diversity of trees which results in even lower variance of the fit model. 

Run the following code cell and compare the three models. 

# Lecture 7. Parametric vs. Nonparametric modeling: The $k$-Nearest Neighbors Algorithm

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RandyRDavila/Data_Science_and_Machine_Learning_Spring_2022/blob/main/Lecture_7/Lecture_7_1.ipynb)


What is a parameter in a machine learning model?
A **model parameter** is a configuration variable that is internal to the model and whose value can be estimated from the given data.
* They are required by the model when making predictions.
* Their values define the skill of the model on your problem.
* They are estimated or learned from historical training data.
* They are often not set manually by the practitioner.
* They are often saved as part of the learned model.

The examples of model parameters include:
* The weights in an artificial neural network.
* The coefficients in linear regression or logistic regression.

Machine learning algorithms are classified into two distinct groups: **parametric** and **nonparametric** models.

1. Parametric models deal with discrete values,and nonparametric models use continuous values.
2. Parametric models are able to infer the traditional measurements associated with normal distributions including mean, median, and mode. While some nonparametric distributions are normally oriented, often one cannot assume the data comes from a normal distribution.
3. Feature engineering is important in parametric models. Because you can poison parametric models if you feed a lot of unrelated features. Nonparametric models handle feature engineering mostly. We can feed all the data we have to those non-parametric algorithms and the algorithm can ignore unimportant features. It would not cause overfitting.
4. A parametric model can predict future values using only the parameters. While nonparametric machine learning algorithms are often slower and require large amounts of data, they are rather flexible as they minimize the assumptions they make about the data.

The single neuron model, i.e., the Perceptron, linear regression, and logistic regression, and deep neural networks, are all examples of parametric machine learning algorithms. This notebook begins are study of **nonparametric machine learning algorithms**. Some examples of popular nonparametric machine learning algorithms are:
* k-Nearest Neighbors
* Decision Trees like CART and C4.5
* Random Forests
* Support Vector Machines

This notebook implements the simpliest of these algorithms, namely, the $k$-nearest neighbors algorithm. 



Notice in the image above that most of the time, similar data points are close to each other. The KNN algorithm hinges on this assumption being true enough for the algorithm to be useful. KNN captures the idea of similarity (sometimes called distance, proximity, or closeness) with some mathematics we might have learned in our childhood— calculating the distance between points on a graph.


## Choosing the right value for K
To select the K that’s right for your data, we run the KNN algorithm several times with different values of K and choose the K that reduces the number of errors we encounter while maintaining the algorithm’s ability to accurately make predictions when it’s given data it hasn’t seen before.

Here are some things to keep in mind:

1. As we decrease the value of K to 1, our predictions become less stable. Just think for a minute, imagine K=1 and we have a query point surrounded by several reds and one green (I’m thinking about the top left corner of the colored plot above), but the green is the single nearest neighbor. Reasonably, we would think the query point is most likely red, but because K=1, KNN incorrectly predicts that the query point is green.
2. Inversely, as we increase the value of K, our predictions become more stable due to majority voting / averaging, and thus, more likely to make more accurate predictions (up to a certain point). Eventually, we begin to witness an increasing number of errors. It is at this point we know we have pushed the value of K too far.
3. In cases where we are taking a majority vote (e.g. picking the mode in a classification problem) among labels, we usually make K an odd number to have a tiebreaker.

### Then how to select the optimal K value?
* There are no pre-defined statistical methods to find the most favorable value of K.
* Initialize a random K value and start computing.
* Choosing a small value of K leads to unstable decision boundaries.
* The substantial K value is better for classification as it leads to smoothening the decision boundaries.
* Derive a plot between error rate and K denoting values in a defined range. Choose the K value having the minimum error rate. 

### Advantages
* The algorithm is simple and easy to implement.
* There’s no need to build a model, tune several parameters, or make additional assumptions.
* The algorithm is versatile. It can be used for classification, regression, and search (as we will see in the next section).


### Disadvantages
* The algorithm gets significantly slower as the number of examples and/or predictors/independent variables increase.
### The KNN Algorithm
1. Load the data
2. Initialize K to your chosen number of neighbors
3. For each example in the data
 - 3.1 Calculate the distance between the query example and the current example from the data.
 - 3.2 Add the distance and the index of the example to an ordered collection
4. Sort the ordered collection of distances and indices from smallest to largest (in ascending order) by the distances
5. Pick the first K entries from the sorted collection
6. Get the labels of the selected K entries
7. If regression, return the mean of the K labels
8. If classification, return the mode of the K labels


Before implementing this algorithm we creat a training set and testing set by running the following code.

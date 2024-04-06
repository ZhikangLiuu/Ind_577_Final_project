#  Linear Regression Model

Let $\mathcal{X}$ be the space of all possible feature vectors, let $\mathcal{Y}$ be the space of all possible corresponding labels for the feature vectors, and let $f:\mathcal{X} \rightarrow \mathcal{Y}$ be the optimal target function assigning labels to feature vectors in $\mathcal{Y}$. Next recall that in supervised machine learning we observe some subset of features and labels as shown in the figure below. 

---
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/423f171b-6ab8-499e-a058-b58552213b81)
---

In [regression](https://favtutor.com/blogs/types-of-regression), machine learning models are given labeled data $\mathcal{D} = \{(\mathbf{x}^1, y^1), \dots, (\mathbf{x}^N, y^N)\}$, where the feature vectors satisfy $\mathbf{x}^{(i)} \in \mathbb{R}$ and the target labels satify $y^{(i)} \in \mathbb{R}$. Thus, this supervised learning task seeks to predict real valued target labels. This is different from classification (such as the perceptron single neuron model) as the following figure suggests.

We will focus on **linear regression**. This specific case of regression assumes that the target values in $\mathcal{Y}$ are approximated by a linear function of the associated feature vectors. In summary, our goal is to approxiate this function $f(x)=y$ with mechine learning way.

---
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/b42f6015-2799-426a-8538-a6f0476c5b1b)
---

## Algorithm
In this model the optimal target function $f:\mathcal{X} \rightarrow \mathcal{Y}$ assigns the correct labels to every possible feature measurement. Next recall that our goal is to find a reasonable hypthesis $h:\mathcal{X} \rightarrow \mathcal{Y}$, which approximates the target function $f$. 

we are assuming the target function $f:\mathcal{X} \rightarrow \mathcal{Y}$ is a **linear function of the input features**, and because we know single neuron models are good function approximators, we next build a single neuron model with a *linear-activation* activation function. Furthermore, in this model we choose the *mean-sqaured error* cost function:

$$
C(\mathbf{w}, b) = \frac{1}{2N}\sum_{i=1}^{N}\Big(\hat{y}^{(i)} - y^{(i)}\Big)^2. 
$$

With our specific case of linear regression on the setosa iris dataset with a single feature measurment taken from sepal length data, we next construct a single neuron model with a linear activation function and the mean-sqaured error cost function as depicted in the figure below.

---
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/59c6364a-87d5-46e2-b456-34ed496b555c)
---

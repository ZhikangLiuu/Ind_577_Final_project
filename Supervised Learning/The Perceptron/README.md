# Introduction of The Perceptron
The Perceptron algorithm is a type of artificial neuron conceived by Frank Rosenblatt in 1957 and can be seen as the simplest form of a neural network. It's a foundational element of machine learning and has informed the development of more complex models.
The perceptron is a single neuron model with sign activation function as depicted in the figure below.
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/07114d5b-c988-4f94-856f-c8a6c43f02f6)

A perceptron takes several binary inputs, multiplies each by a weight, sums them up, adds a bias (also known as the intercept), 
and then passes the sum through an activation function to produce a single binary output.

## Model Structure
A Perceptron is a binary classifier that maps its input $x$ (a vector of real numbers) to an output value $f(x)$ which is typically binary (0 or 1). It consists of the following components:
- Inputs ( $x^{(i)}_1,x^{(i)}_2$ ):The inputs to the perceptron are denoted as $x^{(i)}_1$ and $x^{(i)}_2$ 

- Weights ( $w_1, w_2$ ): Each input feature has an associated weight which indicates the strength of the influence of that feature on the output. 

- Bias ( $b$ ): This is similar to the intercept term in a linear equation. It allows the activation threshold to be adjusted.

- Activation ( $z$ ): This is the weighted sum of the inputs plus the bias, which is the computation before the activation function is applied. Mathematically, this is represented as: $z= w_1x^{i}_1+w_2x^{i}_2+b $
- Activation Function ( $\phi(z)$ ): The perceptron uses an activation function to transform the weighted sum into an output. If output will be 1 if $z$ is 0 or postive and will be -1 if $z$ is negetive.

- Output ( $\hat{y}^{(i)}$ ): This is the final prediction of the perceptron for the input example $i$.

## Algorithm

1. Initialize the weights and bias to zero or a small random value.
2. For each training sample $x^{(i)}$ perform the following steps:
   
   (a) Compute the output value $\hat{y}^{(i)}$ using the current weights and bias.
   
   (b) Update the weights and bias if $\hat{y}^{(i)}$ does not match the actual target $y^{(i)}$ as follow:
       $$
         w = w+ \alpha(y^{(i)}-\hat{y}^{(i)})x^{(i)} \\
         b = b+ \alpha(y^{(i)}-\hat{y}^{(i)})
       $$
   Here, $\alpha$ is the learning rate, a hyperparameter that determines the step size during the learning process.
   
## Application
The Perceptron has found various applications across different fields. Some of the key applications of the Perceptron include:

- Pattern Recognition: One of the earliest applications of perceptrons was in pattern recognition tasks. For instance, perceptrons have been used to classify handwritten characters in optical character recognition (OCR) systems.
  
- Binary Classification: Perceptrons are particularly suited for binary classification tasks where the goal is to classify input data into one of two categories. For example, perceptrons can be employed in spam email detection systems to classify emails as either spam or non-spam.
  
- Medical Diagnosis: Perceptrons have been utilized in medical diagnosis applications, such as classifying medical images to identify the presence of diseases or anomalies.
  
- Predictive Modeling: Perceptrons can be used for predictive modeling in various domains, including finance, marketing, and engineering. They can help predict outcomes based on input features, aiding in decision-making processes.
  
- Signal Processing: Perceptrons can be applied in signal processing tasks, such as filtering noisy signals or detecting patterns in time-series data.

## Limits 

**Linear Separability:** A single Perceptron can only learn linearly separable patterns. It cannot model complex relationships or solve non-linear problems like the XOR problem.

**No Probability Estimates:** Perceptrons do not output probabilities; they only provide a class label.So it can not be used to solve regression problem.

---
**Example**:
Let's say we have a perceptron that determines whether an email is spam (output 1) or not spam (output -1), with the inputs being specific features detected in the email:
- $x^{(i)}_1$: Presence of the word "deal" (1 if present, 0 if not)
- $x^{(i)}_2$: Frequency of uppercase letters (normalized to a value between 0 and 1)
  
Given weights and bias:
- $w_1 = 0.5$
- $w_2 = 0.5$
- $b = -0.7$
  
For an email that contains the word "deal" and has a high frequency of uppercase letters (let's say $x^{(i)}_2 = 0.8$):
The pre-activation calculation would be:
$$z = (0.5 \times 1) + (0.5 \times 0.8) - 0.7 = 0.3 $$
Since $z = 0.3$ is greater than 0, the activation function will output 1:
$$\hat{y}^{(i)} = \phi(0.3) = 1 $$
The email would be classified as spam according to the perceptron's decision boundary.

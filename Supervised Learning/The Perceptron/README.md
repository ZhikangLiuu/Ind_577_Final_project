# Introduction of The Perceptron
The Perceptron algorithm is a type of artificial neuron conceived by Frank Rosenblatt in 1957 and can be seen as the simplest form of a neural network. It's a foundational element of machine learning and has informed the development of more complex models.
The perceptron is a single neuron model with sign activation function as depicted in the figure below.
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/07114d5b-c988-4f94-856f-c8a6c43f02f6)

A perceptron takes several binary inputs, multiplies each by a weight, sums them up, adds a bias (also known as the intercept), 
and then passes the sum through an activation function to produce a single binary output.

## Model Structure
A Perceptron is a binary classifier that maps its input $x$ (a vector of real numbers) to an output value $f(x)$ which is typically binary (0 or 1). It consists of the following components:
- **Inputs ( $x^{(i)}_1,x^{(i)}_2$ ):** The inputs to the perceptron are denoted as $x^{(i)}_1$ and $x^{(i)}_2$ 

- **Weights ( $w_1, w_2$ ):** Each input feature has an associated weight which indicates the strength of the influence of that feature on the output. 

- **Bias ( $b$ ):** This is similar to the intercept term in a linear equation. It allows the activation threshold to be adjusted.

- **Activation ( $z$ ):** This is the weighted sum of the inputs plus the bias, which is the computation before the activation function is applied. Mathematically, this is represented as: $z= w_1x^{i}_1+w_2x^{i}_2+b $
- **Activation Function ( $\phi(z)$ ):** The perceptron uses an activation function to transform the weighted sum into an output. If output will be 1 if $z$ is 0 or postive and will be -1 if $z$ is negetive.

- **Output ( $\hat{y}^{(i)}$ ):** This is the final prediction of the perceptron for the input example $i$.

## Algorithm

1. Initialize the weights and bias to zero or a small random value.
2. For each training sample $x^{(i)}$ perform the following steps:
   
   (a) Compute the output value $\hat{y}^{(i)}$ using the current weights and bias.
   
   (b) Update the weights and bias if $\hat{y}^{(i)}$ does not match the actual target $y^{(i)}$ as follow:
       $$w = w+ \alpha(y^{(i)}-\hat{y}^{(i)})x^{(i)}$$
       $$b = b+ \alpha(y^{(i)}-\hat{y}^{(i)})$$
   Here, $\alpha$ is the learning rate, a hyperparameter that determines the step size during the learning process.
   
## Application
The Perceptron has found various applications across different fields. Some of the key applications of the Perceptron include:

- Pattern Recognition: One of the earliest applications of perceptrons was in pattern recognition tasks. For instance, perceptrons have been used to classify handwritten characters in optical character recognition (OCR) systems.
  
- Binary Classification: Perceptrons are particularly suited for binary classification tasks where the goal is to classify input data into one of two categories. For example, perceptrons can be employed in spam email detection systems to classify emails as either spam or non-spam.
  
- Medical Diagnosis: Perceptrons have been utilized in medical diagnosis applications, such as classifying medical images to identify the presence of diseases or anomalies.
  
- Predictive Modeling: Perceptrons can be used for predictive modeling in various domains, including finance, marketing, and engineering. They can help predict outcomes based on input features, aiding in decision-making processes.
  
- Signal Processing: Perceptrons can be applied in signal processing tasks, such as filtering noisy signals or detecting patterns in time-series data.

## Advantages

- **Simplicity:** The perceptron is one of the simplest forms of a neural network, which makes it easy to understand and implement. It is essentially a linear classifier used for binary classification tasks.

- **Efficiency:** Training a perceptron is computationally inexpensive because it uses a simple learning algorithm, often called the perceptron learning rule. This rule adjusts the weights based on the error of the output compared to the expected result, making only small updates for each training example.

- **Online Learning:** The perceptron can learn and adapt as new data comes in, without needing to retrain from scratch. This makes it suitable for systems that receive data sequentially and need incremental updates.

## Disadvantages

- **Linear Separability Limitation:** The perceptron can only classify linearly separable data sets. If the data cannot be separated by a straight line, the perceptron will not converge to a solution, which significantly limits its applicability.
- **Lack of Probability Estimation:** Perceptrons do not output probabilities but rather make hard classifications. This can be a limitation in applications where you need to know the confidence of predictions.
- **Prone to Overfitting:** If the training data is noisy or if the perceptron is trained for too many epochs, it can overfit to the training data, leading to poor generalization to new data.





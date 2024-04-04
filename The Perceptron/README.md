# The Perceptron
The perceptron is a single neuron model with sign activation function as depicted in the figure below.
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/07114d5b-c988-4f94-856f-c8a6c43f02f6)

A perceptron takes several binary inputs, multiplies each by a weight, sums them up, adds a bias (also known as the intercept), 
and then passes the sum through an activation function to produce a single binary output.

## Illustration

- Inputs ( $x^{i}_1,x^{i}_2$ ):The inputs to the perceptron are denoted as $x^{i}_1$ and $x^{i}_2$ 

- Weights ( $w_1, w_2$ ): Each input feature has an associated weight which indicates the strength of the influence of that feature on the output. 

- Bias ($b$): This is similar to the intercept term in a linear equation. It allows the activation threshold to be adjusted.

- Pre-Activation ( $z$ ): This is the weighted sum of the inputs plus the bias, which is the computation before the activation function is applied. Mathematically, this is represented as: $$ z= w_1x^{i}_1+w_2x^{i}_2+b $$
- Activation Function ( $\phi(z)$ ): The perceptron uses an activation function to transform the weighted sum into an output. If output will be 1 if $z$ is 0 or postive and will be -1 if $z$ is negetive.

- Output ( $\hat{y}^{(i)}$ ): This is the final prediction of the perceptron for the input example $i$.


---
**Example**:
Let's say we have a perceptron that determines whether an email is spam (output 1) or not spam (output -1), with the inputs being specific features detected in the email:
- \( x^{(i)}_1 \): Presence of the word "deal" (1 if present, 0 if not)
- \( x^{(i)}_2 \): Frequency of uppercase letters (normalized to a value between 0 and 1)
Given weights and bias:
- \( w_1 = 0.5 \)
- \( w_2 = 0.5 \)
- \( b = -0.7 \)
For an email that contains the word "deal" and has a high frequency of uppercase letters (let's say \( x^{(i)}_2 = 0.8 \)):
The pre-activation calculation would be:
$$ z = (0.5 \times 1) + (0.5 \times 0.8) - 0.7 = 0.3 $$
Since \( z = 0.3 \) is greater than 0, the activation function will output 1:
$$ \hat{y}^{(i)} = \phi(0.3) = 1 $$
The email would be classified as spam according to the perceptron's decision boundary.






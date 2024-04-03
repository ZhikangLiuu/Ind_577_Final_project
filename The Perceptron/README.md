## The Perceptron
The perceptron is a single neuron model with sign activation function as depicted in the figure below.
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/07114d5b-c988-4f94-856f-c8a6c43f02f6)

A perceptron takes several binary inputs, multiplies each by a weight, sums them up, adds a bias (also known as the intercept), 
and then passes the sum through an activation function to produce a single binary output.

1.Inputs ($x^{(i)}_1, x^{(i)}_2$): These are the input features for a given training example $i$.

2.Weights ($w_1, w_2$): Each input feature has an associated weight which indicates the strength of the influence of that feature on the output. 

3.Bias ($b$): This is similar to the intercept term in a linear equation. It allows the activation threshold to be adjusted.

4.Pre-Activation ($z$): This is the weighted sum of the inputs plus the bias, which is the computation before the activation function is applied. 
Mathematically, this is represented as:
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/f016b719-ed25-4534-be22-c067d415f6e8)

5.Activation Function ($\phi(z)$): The perceptron uses an activation function to transform the weighted sum into an output. 
In this diagram, a simple step function is used:

\begin{cases}
1 & \text{if } z \geq 0 \\
-1 & \text{if } z < 0
\end{cases} $$

This function will output $1$ if $z$ is zero or positive, and $-1$ if $z$ is negative.

6.Output ($\hat{y}^{(i)}$): This is the final prediction of the perceptron for the input example $i$. 
It's represented by $a$ in the diagram and is equal to the output of the activation function:
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/504a1abc-a73f-4187-b6dd-67b3071284dc)

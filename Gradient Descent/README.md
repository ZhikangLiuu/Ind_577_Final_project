## Gradient Descent

The goal of Gradient Descent is to minimize a function and it is often the loss function given by your own optimization.
Giving a convex function, you pick one point to start.Suppose your function is given by $y=f(x)= (x-2)**2+1$, initial 
$x_0$ is 5 and you want to minimize this function.
The idea to minimize this function is to find the gradient for your points and go along the gradient to reduce the value of 
this function. It is like you are on a hill and you have to walk down the slope of the hill to reach the lowest point。

![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/97d31d07-9de5-49d5-8926-cd8e4256a5ff)

There are some steps of this algorithm：
- find the slope of initial point $f'(w) = 2(w - 2)$
- set your arriving point $$w_{n+1} = w_n - \alpha f'(w_n) $$
- compute and get $w_{n+1}$
- repeat untill it reaches your stopping condition

The figure shows this process:
![image](https://github.com/ZhikangLiuu/Ind_577_Final_project/assets/165843914/1ce0cfa0-307a-4bb4-8cc5-bd0b6e16e76e)



---
layout: post
title:  "Linear regression for ML"
date:   2022-10-03 20:26:21 +0200
use_math: true
categories: jekyll update
---



> __Linear regression__ aims to find the best fit straight line between input variable(s) and a output variable. It is a linear model, i.e. a model that assumes a linear relationship between the input variable(s) (x) and the output variable (y). It means y can be expressed as a linear expression of the variable(s) x. 

Note: real world scenarios normally have multiple input variables. Example: real estate prices can be based on area, location, standard, age etc.

# Features (variables)
Features (ML lingo) are the variables in the linear expression.    

$$
X = 
\begin{bmatrix}
x_0 \\x_1 \\ x_2 \\ \vdots \\ x_n 
\end{bmatrix}
\in R^{n+1}
$$

$R^{n+1}$ is a vector of n+1 real numbers. (a n+1 dimensional vector)

# Parameters
Parameters are the constants of the features (variables) in the linear expression.  
The aim is that the algorithm learns the parameters through training, in order to fit the linear expression to do predictions. 

$$
\theta = 
\begin{bmatrix}
\theta_0 \\ \theta_1 \\ \theta_2 \\ \vdots \\ \theta_n 
\end{bmatrix}
\in R^{n+1}
$$

# Hypothesis
Hypothesis = the equation that gets features and parameters as input and predicts a value as output.

$$ h_{\theta}(x) = X^{T}\theta = \theta_0 x_0 + \theta_1 x_1 + \theta_2 x_2 + \dots + \theta_n x_n $$

For convenience, $x_0$ is inserted and set $x_0 = 1$, as $\theta_0$ is a constant. 

# Cost Function
Shows how accurate the predictions of the hypothesis are with the current parameters.

$$ J(\theta) =  \frac{1}{2m}\sum_{i=1}^{m}(h_{\theta}(x^{(i)}) - y^{(i)})^{2} $$

$x^i$: input(features/variables) of $i^{th}$ training example  
$y^i$: output of $i^{th}$ training example  
$m$: number of training examples  


# Batch Gradient Descent
An iterative optimization algorithm for finding the minimum of a cost function.
> The term "batch" means that each step of gradient descent uses **all** the training examples.

$$ \theta_j :=  \theta_j -\alpha \frac{\delta}{\delta \theta_j}J(\theta) $$

$$ \theta_j :=  \theta_j -\alpha \frac{1}{m}\sum_{i=1}^{m}(h_{\theta}(x^{(i)}) - y^{(i)})x_j^{(i)} $$

for j = 0, 1, ..., n.   
n : number of features  
$\alpha$ : the learning rate  
$x_j^{(i)}$ : $j^{th}$ feature of the $i^{th}$ training example  

# Feature scaling
> Features must be on a similar scale when doing linear regression with gradient descent.

$$ -1 \leq x_i \leq 1$$

For example, apartment area will be on a different scale than number of rooms (e.g. $100m^2$ vs 3 rooms).

Scaling is done with **mean normalization**.

$$x_j^{(i)}=\frac{x_j^{(i)}- \mu_j}{s_j}$$

$\mu_j$ : average value of $j^{th}$ feature set.  
$s_j$  : the range (max-min) of $j^{th}$ feature in training set.  

# Polynomial Regression
A form of regression analysis where the relationship between input variable x and output variable y is modelled as a $n^{th}$ degree polynomial.

The hypothesis function is still linear for polynomial regression, so even if the model is nonlinear, it is a linear problem in statistical sense. It is considered a special case of multiple linear regression.

$$ h_{\theta}(x) =   \theta_0 + \theta_1 x_1 + \theta_2 x_2 + \theta_3 x_3 = \theta_0 + \theta_1(size) + \theta_2(size)^2 + \theta_3(size)^3 $$




[Source](https://github.com/trekhleb/homemade-machine-learning/tree/master/homemade/linear_regression)
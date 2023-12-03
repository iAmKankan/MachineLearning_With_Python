## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Logistic Regression Assumptions](#logistic-regression-assumptions)
* [Logistic Regression Definition](#logistic-regression-definition)
* [What is Regression](#what-is-regression)
* [Difference between Linear Regression and Logistic Regression](#difference-between-linear-regression-and-logistic-regression)
* Logistic Regression Approaches
   * Probabilistic Appraoch
   * Geometric Approach (Distance Based Approach)
   * Log-Loss Based Approach
   
   
### ⬛ Binary Classification
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

### 🔲 Problem with Linear Regression for Binary Classification
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
Suppose we have two classes **red class** or the **blue class** which is class **1** or $\mathbf{x_1}$ or class **0** or $\mathbf{x_2}$. So, our label **y** should always be either **0** or **1**.

<p align="center" >
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/dd33d76f-9c99-42ea-9b75-7a6f8853da32" width=31%/>  <img src="https://user-images.githubusercontent.com/12748752/186803012-94d84921-f53d-4789-9d8c-340375c23edf.png" width=40%/>
  <br> <ins><b><i>Linear model to perform Binary Classification; X<sup>&#8407;</sup>	 is the input vector</i></b></ins>
 </p>  

###  The problem
If I had fit a simple **_linear regression line_**, in a **linear model**  $\large{\color{Purple} \hat{y}=w_0+w_1 x_1+w_2 x_2}$ and introduce a point(data) far in **red** class then-
* Regardless of your weights $\large{\color{Purple}w_1}$ and $\large{\color{Purple}w_2}$ if I pick up that far away point then above $\large{\color{Purple} \hat{y}}$ value will come **very high** _it is not going to lie between **0** and **1**_. 
* Similarly if I choose _a point at the extreme blue class_, there is no way for you to ensure that a **_simple linear model_** will always give values between **0** and **1**.

### 🔲 Solution of this problem
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

As a solution we use a very simple idea which is too **_squish_** all data to the range **[0, 1 ]** which is what we require as our output, by introducing a **sigmoid (&sigma;)**

$$ {\color{Purple}
\Huge \mathbf{\sigma (z) \equiv \frac{1}{1+ e^{-z}} }
 \large\begin{cases}
As \textbf{ z} \to \infty & , \sigma(z) \to 1 \\
As \textbf{ z} \to - \infty & , \sigma(z) \to 0 \\
As \textbf{ z} = 0 &, \sigma(z) = 0.5 \\
\end{cases}
}
$$

<p align="center">
<img src="https://user-images.githubusercontent.com/12748752/186841982-9a9a3b1f-76a8-456a-b8ca-ced8bc4c89c5.png" width=30% />
  <br> <ins><b><i>Sigmoid Curve</i></b></ins>
</p>   


If I use **Sigmoid** of linear regression, this would tell me that $\large{\color{purple}\hat{y}}$ will always lie between $\large{\color{purple}0}$ and $\large{\color{purple}1}$. 

Now this has an additional advantage which is now we can **interpret** Means- $\large{\color{purple}\hat{y}}$ as the **Probability** that the output belongs to **class 1** even the **input x**

$$\large{\color{purple}\hat{y} = P(y=1|x)}$$

 Let me explain-

<p align="center">
<img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/e382c65b-67c0-483d-ba91-9d5cc75f299c" width=60% />
  <br> <ins><b><i></i></b></ins>
</p>   

Now let us look at this classification line there, we want this value  $\large{\color{purple} \hat{y} = \sigma({\color{red}\boxed{{\color{purple}w_0+w_1 x_1+w_2 x_2}}})}$ be called as $\large{\color{purple}z}$ , such that if it has to lie in **class 1** then z has to be really high  $\large{\color{purple} z>0}$. If it has to belong to **class 0** we know that z has to be really low $\large{\color{purple} z<0}$.

Now suppose I look at a new point which is there in **red dotted circle**, what this tells me is that this point is almost certain to lie in **class 1**. Just looking at this data the further away we get away from this **classifying line** then more and more certain we are that this point belongs to **class 1**. Similarly, the further away we get to decide of the line, the further and further closer certain we are that we belong to **class 0** . So what we can think of z as- **z is the perpendicular distance from the classifying line**.

How does that help us? 
* The classifying line is $\large{\color{purple}z=0}$ which means $\large{\color{purple}\sigma ( z) = 0.5}$ ,
* if I come to this Red side $\large{\color{purple}\sigma ( z)}$  becomes close to 1,
* if I come to this Blue side $\large{\color{purple}\sigma ( z)}$ becomes close to 0,

  The closer I am to this **Classification line** the more uncertain we are about where the result lies, whether it lies on **class 1** or whether it lies on **class 0**. Therefore it is easy to now interpret $\large{\color{purple}\hat{y}}$ which was equal to $\large{\color{purple}\sigma ( z)}$ as the probability that you belong to **class 1**, for example- if your **Sigmoid** value is close to **0.5** okay then what it means is you are not really certain about how close it is to **class 1**, it means probability is approximately **0.5** that it is **class 1**.

Let us see sigmoid is close to 0.99 , then we know that it is really far away and that we are very-very certain that it lies in **class 1**. Suppose the **Sigmoid** value is **0.01** then we know that the probability that it lies in **class 1** is actually pretty low it is equal to **0.01**. So this is the simple idea behind logistic regression.

$${\color{Purple}
\begin{matrix}
\huge \mathbf{\hat{y} = \sigma} (w_0+w_1x_1+w_2x_2) & \\
& \large \mathbf{\Rightarrow \hat{y} \in [0, 1]} \\
& \textrm{Interprit } \large \mathbf{\hat{y} = p(y=1|x)}\\
& \large \mathbf{\hat{y} = \sigma(z) = p(y=1|x)}
\end{matrix}
}
$$

### 🔲 Multinomial Classification for Logistic Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

### We need to know the followings-
1) How do we represent the output class(label): Catagorical=Horse,Dogs,Cats or One-Hot-Vector.
2) What happens to the final layer- In Binary classification task we use the **sigmoid** function, because it neatly gave us a number **between 0 and 1**. Now in a multinomial classification case we use **Softmax** function, which actually corresponds very well with the **One Hot Vector**.
3) How we are going to look at the loss function for multinomial classification.







### Cost function for Logistic Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

##### This was our forward model Logistic regression 

$${\color{Purple}
\huge \mathbf{\hat{y} = \sigma(w . x)} 
\large \begin{cases}
w = [w_0, w_1, \cdots,w_n]^{\top} \\
x =[x_1,x_2, \cdots, x_n]
\end{cases}
}
$$

Now the question is what is a good **cost function** for this? in our usual learning paradigm what we have is
* I have an input $\large{\color{purple}x}$, this **predicts** a $\large{\color{purple}?math=\hat{y}}$, the **ground truth** is some $\large{\color{purple}y}$ , and I wish to find out some cost or penalty for $\large{\color{purple}?math=\hat{y}}$ and $\large{\color{purple}y}$ being different.

#### Why _Least Square_ cost function BAD for Logistic regression?
What we do for **linear regression**  we take the sum of all these examples and take an average that is .

$$ {\color{Purple} \large \mathbf{J^{LS} = \frac{1}{2} (y- \hat{y})^2} }$$


But it is not a good cost function for classification because the cost that you incur for misclassification, that is when <img src="https://latex.codecogs.com/svg.image?\large&space;\large{\color{Purple}y}" title="https://latex.codecogs.com/svg.image?\large \large{\color{Purple}y}" /> is **0** if you say <img src="https://latex.codecogs.com/svg.image?\large&space;\large{\color{Purple}\hat{y}}" title="https://latex.codecogs.com/svg.image?\large \large{\color{Purple}\hat{y}}" /> is **1** or close to 1 let us say 0.99, so when we want to predict something as clear as classification and you give a misclassification, the cost incurred for that is actually very low, that is we do not penalize this cost high enough, even though there is a penalty it is not high enough. So because of that, this is one of the reasons why the usual least square cost function is a bad cost function for classification.

### _Binary cross entropy_ cost function

$$ {\color{Purple} \Huge \boxed{\mathbf{ J= - \Bigl\\{ y \ln\hat{y} + (1-y) \ln(1-\hat{y}) \Bigl\\} }} }$$

* So, $\large{\color{Purple} y}$ is either a **0** or **1**, $\large{\color{Purple} \hat{y}}$ is between **0** and **1**. 
* Therefore $\large{\color{Purple} \ln \hat{y}}$ is going to be **negative (-ve)** . 
* $\large{\color{Purple} y}$ is going to be either **0** or **1**, 
* So this whole term Therefore $\large{\color{Purple} y \ln \hat{y}}$ is **negative (-ve)**. 
* Similarly this term Therefore $\large{\color{Purple} (1 − y ) \ln(1− \hat{y})}$  is also **negative (-ve)**, and that is why we have minus sign so that the whole term actually becomes positive. So that it is consistent with least squares.

#### Desirable properties for classification cost function-
1. $\large{\color{Purple} \mathbf{J = 0} \textit{, if } \mathbf{y=\hat{y}} }$
2. $\large{\color{Purple} \mathbf{J} \textrm{ would be very high for }\mathbf{missclassification}}$
3. $\large{\color{Purple} \mathbf{J \geq 0}}\textrm{    [required for consistency]}$

#### 1. For $\large{\color{Purple} \mathbf{J = 0} \textit{, if } \mathbf{y=\hat{y}} }$ and for  $\large{\color{Purple} \mathbf{J \geq 0}}$
#### Example
* Suppose $\large \mathrm{y=0, \ \  \hat{y}=0} \textrm{ or close to 0, } \mathbf{ J \approx 0} $
* Suppose $\large \mathrm{y=1, \ \  \hat{y} \approx 1} ,  \mathbf{ J \approx 0} $
* Suppose $\large \mathrm{y=0, \ \  \hat{y} \approx 1} ,  \mathbf{ J \to \infty} $

#### 2. For $\large{\color{Purple} \mathbf{J} \textrm{ would be very high for }\mathbf{missclassification}}$
##### The equation

$$ {\color{Purple} \large \mathbf{ J= - \Bigl\\{ y \ln\hat{y} + (1-y) \ln(1-\hat{y}) \Bigl\\} }}$$



* $\large{\color{Purple} y=0,} \textrm{ makes this term } {\color{Purple}(y \ln\hat{y}) = 0 } $ 
* $\large{\color{Purple} y=0,} \textrm{ makes this term } {\color{Purple}((1-y)) \approx 0 } \textrm{ and } {\color{Purple} \hat{y} \approx 0,} \textrm{ makes this term } {\color{Purple}((1-\hat{y})) \approx 0 } $
* So, $\large{\color{Purple} \ln 0 = - \infty } $ 
* $\large{\color{Purple} y=0, \hat{y} \approx 1 \Rightarrow  \mathbf{J} \to \infty } \textrm{, Hence proved } $
* $\large{\color{Purple} y=1, \hat{y} \approx 0 \Rightarrow  \mathbf{J} \to \infty } \textrm{, Hence proved } $



![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
## Logistic Regression
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* Logistic regression is one such regression algorithm which can be used for performing classification problems. 
* It calculates the probability that a given value belongs to a specific class. 
   * If the probability is more than 50%, it assigns the value in that particular class 
   * else if the probability is less than 50%, the value is assigned to the other class. 
* Therefore, we can say that logistic regression acts as a binary classifier.

### Working of a Logistic Model
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* For linear regression, the model is defined by:
<img src="https://latex.codecogs.com/svg.image?\mathbf{y\&space;=\&space;}&space;\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x}\cdots&space;\cdots\cdots(\mathrm{\textbf{i}})" title="\mathbf{y\ =\ } \mathbf{\beta_0} + \mathbf{\beta_{1}x}\cdots \cdots\cdots(\mathrm{\textbf{i}})" width=25% />

* And for logistic regression, we calculate probability. _i.e. **_y_** is the probability of a given variable **_x_** belonging to a certain class_. 
* Thus, it is obvious that the value of y should lie between **_0_** and **_1_**.
* But, when we use equation(i) to calculate probability, we would get values less than **0** as well as greater than **1**. Which doesn’t make any sense
* So, we need to use such an equation which always gives values between **0** and **1**, as we desire while calculating the probability.
* We use the **sigmoid function** as the underlying function in Logistic regression. 

<img src="https://user-images.githubusercontent.com/12748752/155903849-f8ab533c-74c3-440a-b5ea-920c0c7f4e04.PNG" width=50%>

<ins> ***Mathematically and graphically representation of Logistic Regression*** </ins>

### Why do we use the _Sigmoid Function_?
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
1)	The sigmoid function’s range is bounded between **0** and **1**. Thus it’s useful in calculating the probability for the  Logistic function.
2)	It’s derivative is easy to calculate than other functions which is useful during **gradient descent calculation**.
3)	It is a simple way of introducing **non-linearity** to the model.

* Although there are other functions as well, which can be used, but sigmoid is the most common function used for logistic regression.
> ### Probabilistic proof
* The logistic function is given as:
<img src="https://latex.codecogs.com/svg.image?P(X)\&space;=&space;\&space;\frac{e^{\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x}}}{1&plus;e^{\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x}}}" title="P(X)\ = \ \frac{e^{\mathbf{\beta_0} + \mathbf{\beta_{1}x}}}{1+e^{\mathbf{\beta_0} + \mathbf{\beta_{1}x}}}" width=15% />

> #### Let’s see some manipulation with the logistic function: 
<img src="https://latex.codecogs.com/svg.image?\begin{matrix}\cdots\cdots\cdots\cdots\cdots\cdots\cdots\cdots\\\left&space;|&space;\&space;p(X)\&space;=&space;\&space;\frac{1}{1&plus;e^{-(\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x)}}}\&space;&space;\right|&space;\\\cdots\cdots\cdots\cdots\cdots\cdots\cdots\cdots\\&space;&space;\end{matrix}" title="\begin{matrix}\cdots\cdots\cdots\cdots\cdots\cdots\cdots\cdots\\\left | \ p(X)\ = \ \frac{1}{1+e^{-(\mathbf{\beta_0} + \mathbf{\beta_{1}x)}}}\ \right| \\\cdots\cdots\cdots\cdots\cdots\cdots\cdots\cdots\\ \end{matrix}" width=20% />
 
<img src="https://latex.codecogs.com/svg.image?\\p(X)\&space;=&space;\&space;\frac{1}{1&plus;e^{-(\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x)}}}&space;\cdots&space;\cdots\cdots\cdots&space;\cdots&space;(1)\\&space;\\&space;1-&space;p(X)\&space;=&space;1&space;-&space;\frac{e^{h(0)}}{1&plus;e^{h(0)}}&space;\&space;,\&space;h(0)=&space;\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x}&space;\\&space;\\1-&space;p(X)\&space;=&space;1&space;-&space;\frac{1}{1&plus;e^{h(0)}}&space;\&space;=\&space;\frac{1}{1&plus;e^{\beta_0&space;&plus;&space;&space;\beta_{1}x}}&space;\cdots\cdots\cdots&space;(2)\\" title="\\p(X)\ = \ \frac{1}{1+e^{-(\mathbf{\beta_0} + \mathbf{\beta_{1}x)}}} \cdots \cdots\cdots\cdots \cdots (1)\\ \\ 1- p(X)\ = 1 - \frac{e^{h(0)}}{1+e^{h(0)}} \ ,\ h(0)= \mathbf{\beta_0} + \mathbf{\beta_{1}x} \\ \\1- p(X)\ = 1 - \frac{1}{1+e^{h(0)}} \ =\ \frac{1}{1+e^{\beta_0 + \beta_{1}x}} \cdots\cdots\cdots (2)\\" width=40% />

* If we Divide `(1)` by `(2)` we will get-
<img src="https://latex.codecogs.com/svg.image?\\&space;\frac{p(X)}{1&space;-&space;p(X)}=e^{(\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x)}" title="\\ \frac{p(X)}{1 - p(X)}=e^{(\mathbf{\beta_0} + \mathbf{\beta_{1}x)}" width=20%/>

* Lets take _Log_ at each side, we will get Logit Function
<img src="https://latex.codecogs.com/svg.image?\\&space;log\left&space;(\frac{p(X)}{1&space;-&space;p(X)}&space;&space;\right&space;)=\&space;\mathbf{\beta_0}&space;&plus;&space;\mathbf{\beta_{1}x" title="\\ log\left (\frac{p(X)}{1 - p(X)} \right )=\ \mathbf{\beta_0} + \mathbf{\beta_{1}x" width=30%  />  

* We can see that the logit function is linear in terms with **x**.

> ### Prediction
<img src="https://latex.codecogs.com/svg.image?y=\left\{\begin{matrix}\mathrm{0\&space;\&space;,\&space;\&space;if\&space;\&space;&space;p(X)\&space;<&space;&space;0.5}\\\mathrm{1\&space;\&space;,\&space;\&space;if\&space;\&space;&space;p(X)\&space;\geqslant&space;&space;&space;0.5}\\\end{matrix}\right." title="y=\left\{\begin{matrix}\mathrm{0\ \ ,\ \ if\ \ p(X)\ < 0.5}\\\mathrm{1\ \ ,\ \ if\ \ p(X)\ \geqslant 0.5}\\\end{matrix}\right." />

> ### Cost Function
* for a single 
<img src="https://latex.codecogs.com/svg.image?Cost&space;(\&space;p(X),\&space;y)\&space;\left\{\begin{matrix}-\&space;log(p(X)),&space;\&space;if&space;\&space;y\&space;=\&space;1&space;\\\&space;\&space;\&space;\&space;-\&space;log(1\&space;-\&space;p(X)),&space;\&space;if&space;\&space;y\&space;=\&space;0&space;\end{matrix}\right.&space;" title="Cost (\ p(X),\ y)\ \left\{\begin{matrix}-\ log(p(X)), \ if \ y\ =\ 1 \\\ \ \ \ -\ log(1\ -\ p(X)), \ if \ y\ =\ 0 \end{matrix}\right. " />

* **Why this cost function?**
  * **_if p(x) = 1 and y=1, Cost = 0_**
  * **_if p(x) = 0 and y=0, Cost = 0_**
* **but**
  * **_if p(x) = 0 and y=1, Cost<a>&rarr; &infin; [log(0)&rarr; &infin; ]</a>_**
  * **_if p(x) = 1 and y=0, Cost<a>&rarr; &infin; [log(0)&rarr; &infin; ]</a>_**


* **Cost Function for the whole training set is**
<img src="https://latex.codecogs.com/svg.image?J(\theta)=&space;-\frac{1}{m}\sum_{i=1}^{m}\left&space;[&space;y^{(i)}&space;log(\hat&space;p^{(i)})&plus;(1-y^{(i)})log(1-\hat&space;p^{(i)})\right&space;]" title="J(\theta)= -\frac{1}{m}\sum_{i=1}^{m}\left [ y^{(i)} log(\hat p^{(i)})+(1-y^{(i)})log(1-\hat p^{(i)})\right ]" width=50% />

* The values of parameters (&theta;) for which the cost function is minimum is calculated using the gradient descent (as discussed in the Linear Regression section) algorithm.
* **The partial derivative for cost function is given as :**
<img src="https://latex.codecogs.com/svg.image?\frac{\partial&space;}{\partial&space;\theta_j}\&space;J(\theta)=&space;\frac{1}{m}\sum_{i=1}^{m}\left&space;(&space;\sigma\left&space;(&space;\theta^T&space;x^{(i)}&space;\right&space;)-&space;y^{(i)}\right&space;)x_j^{(i)}" title="\frac{\partial }{\partial \theta_j}\ J(\theta)= \frac{1}{m}\sum_{i=1}^{m}\left ( \sigma\left ( \theta^T x^{(i)} \right )- y^{(i)}\right )x_j^{(i)}" width=35%  />


### Logistic Regression Definition
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* **Regression refers to a set of methods for modeling the relationship between one or more independent variables and a dependent variable.**
* Logestic Regression is a binary classifier that classify your data as a linear separation boundary.
* But unlike Linear Regression the result cann't be infered by drawing a single regression line, like below-
![Blank Diagram](https://user-images.githubusercontent.com/12748752/136457221-4ea7043b-4e18-482c-bd0f-38ee24d8ceb9.png)
* Because, the result is not always 0 and 1. Sometimes may be slight less than 0 or little more than 1. Thats why one regression line is not enough 
* So, anything bigger than 1 we need to clip it and make it 1 similarly anything less than 0 we need to clip it and make it 0. For this we need to draw 3 lines hence it is not differenciable. 
* The Solution is to pass the function _**f(x)**_ (which is = <img src="https://latex.codecogs.com/svg.image?\mathrm{-\infty&space;\textbf{To}&space;&plus;\infty" title="\mathrm{-\infty \textbf{To} +\infty" />) to another function lets _**g()**_ such a way that the result will lies between _**0**_ and _**1**_.
* _**g(f(x))**_ it is called Generalized Linear Model(GLM)
* y= _**g(f(x))**_
    * Where _**g()**_ is a **Identity** function = Linear regression
    * Where _**g()**_ is a **Sigmoid** function = Logistic regression

## Logistic Regression Assumptions
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* There should be a linear relationship in data (data should be linearly separable).
* It assumes that there is minimal or no multicollinearity among the independent variables.
* It usually requires a large sample size to predict properly.
* It assumes the observations to be independent of each other.
* Homoscedasticity: The variance of residual should be the same for any value of X.

## What is Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* [**Please follow the link**](https://github.com/iAmKankan/Statistics/blob/main/commonTerms.md#regression)

### Difference between Linear Regression and Logistic Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

||Range|Domain|
|:---:|:---:|:---:|
|Linear Regression|<img src="https://latex.codecogs.com/svg.image?\mathrm{-\infty&space;\textbf{To}&space;&plus;\infty" title="\mathrm{-\infty \textbf{To} +\infty" />|<img src="https://latex.codecogs.com/svg.image?\mathrm{-\infty&space;\textbf{To}&space;&plus;\infty" title="\mathrm{-\infty \textbf{To} +\infty" />|
|Logistic Regression|_0 or 1_|<img src="https://latex.codecogs.com/svg.image?\mathrm{-\infty&space;\textbf{To}&space;&plus;\infty" title="\mathrm{-\infty \textbf{To} +\infty" />|

#### Sigmoid function
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Sigmoid function = 
> <img src="https://latex.codecogs.com/svg.image?\mathrm{\frac{1}{1&plus;&space;e^{-x}}}" title="\mathrm{\frac{1}{1+ e^{-x}}}" />
* if x= <img src="https://latex.codecogs.com/svg.image?\infty" title="\infty" /> 
    * ⇒ e-∞
    * ⇒ ( 2.71…)-∞
    * ⇒ 1/ e∞ or 1/ (2.71…)∞
    * ⇒ 1/ ∞
    * ⇒ 0
* Hence, if x= <img src="https://latex.codecogs.com/svg.image?\infty" title="\infty" />. Then <img src="https://latex.codecogs.com/svg.image?\mathrm{\frac{1}{1&plus;&space;e^{-x}}}" title="\mathrm{\frac{1}{1+ e^{-x}}}" /> = 1 or very close to 1
* if x= - <img src="https://latex.codecogs.com/svg.image?\infty" title="\infty" /> 
    * ⇒ e∞
    * ⇒ ( 2.71…)∞
* ⇒ 1/ e∞ or 1/ (2.71…)∞
* ⇒ 1/ ∞
* ⇒ 0
* Hence, if x= -<img src="https://latex.codecogs.com/svg.image?\infty" title="\infty" />. Then <img src="https://latex.codecogs.com/svg.image?\mathrm{\frac{1}{1&plus;&space;e^{-x}}}" title="\mathrm{\frac{1}{1+ e^{-x}}}" /> = 0 or very close to 0
 
 ![sigmoid](https://upload.wikimedia.org/wikipedia/commons/thumb/8/88/Logistic-curve.svg/480px-Logistic-curve.svg.png) 

#### How to prove its a Linear Classifier
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

* Since the result can be anything between 0 and 1 we are introducing probability- 
* I am trying to predict _**P**_ probability _**Y=1**_ given for all _**X**_ equls _**1**_ upon _**1**_ plus _**e**_ to-the-power minus _**X**_
---
<img src="https://latex.codecogs.com/svg.image?\mathrm{P(Y=1|X)}=&space;\frac{1}{\mathrm{1}&plus;\mathrm{e^{-X}}&space;}" title="\mathrm{P(Y=1|X)}= \frac{1}{\mathrm{1}+\mathrm{e^{-X}} }" />

---
* This conditional probability assumes the output is equals to _**1**_ by all the inputs of X.
> <img src="https://latex.codecogs.com/svg.image?\mathrm{P}=&space;\frac{1}{\mathrm{1}&plus;\mathrm{e^{-X}}&space;}" title="\mathrm{P}= \frac{1}{\mathrm{1}+\mathrm{e^{-X}} }" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{P}=&space;\frac{1}{\mathrm{1}&plus;\mathrm{e^{-f(x)}}&space;}" title="\mathrm{P}= \frac{1}{\mathrm{1}+\mathrm{e^{-f(x)}} }" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{P}=&space;\frac{1}{\mathrm{1}&plus;\mathrm{e^{-f(x)}}&space;}\times&space;\frac{\mathrm{e^{f(x)}}}{\mathrm{e^{f(x)}}}" title="\mathrm{P}= \frac{1}{\mathrm{1}+\mathrm{e^{-f(x)}} }\times \frac{\mathrm{e^{f(x)}}}{\mathrm{e^{f(x)}}}" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{P}=&space;\frac{\mathrm{e^{f(x)}}}{\mathrm{\mathrm{e^{f(x)}}}&plus;1&space;}" title="\mathrm{P}= \frac{\mathrm{e^{f(x)}}}{\mathrm{\mathrm{e^{f(x)}}}+1 }" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{P}=&space;\mathrm{e^{f(x)}}(\mathrm{1-P})" title="\mathrm{P}= \mathrm{e^{f(x)}}(\mathrm{1-P})" />

> <img src="https://latex.codecogs.com/svg.image?\frac{\mathrm{P}}{\mathrm{1-P}}=&space;\mathrm{e^{f(x)}}" title="\frac{\mathrm{P}}{\mathrm{1-P}}= \mathrm{e^{f(x)}}" />

* Taking log on both sides

> <img src="https://latex.codecogs.com/svg.image?\log&space;\frac{\mathrm{P}}{\mathrm{1-P}}=&space;\log\mathrm{e^{f(x)}}" title="\log \frac{\mathrm{P}}{\mathrm{1-P}}= \log\mathrm{e^{f(x)}}" />

* Log e =1


---
>> <img src="https://latex.codecogs.com/svg.image?\log\left&space;(&space;&space;&space;\frac{\mathrm{P}}{\mathrm{1-P}}\right&space;)=&space;\mathrm{f(x)}" title="\log\left ( \frac{\mathrm{P}}{\mathrm{1-P}}\right )= \mathrm{f(x)}" />  

_**Logistic Regression equation**_ 
____
---

* So, since _**f(x)**_ is a linear function It is to be said that the **Logit** or  **Log of odds** its a linear function so that it alway produce value between **0** and **1**.

> <img src="https://latex.codecogs.com/svg.image?\textrm{It&space;is&space;called&space;'Logit'&space;or&space;'Log&space;of&space;odds'}&space;=&space;\log\left&space;(&space;&space;&space;\frac{\mathrm{P}}{\mathrm{1-P}}\right&space;)" title="\textrm{It is called 'Logit' or 'Log of odds'} = \log\left ( \frac{\mathrm{P}}{\mathrm{1-P}}\right )" />


#### Different representation of Logistic Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

> <img src="https://latex.codecogs.com/svg.image?\mathrm{\sigma(X)=\frac{1}{1&plus;e^{-X}}}" title="\mathrm{\sigma(X)=\frac{1}{1+e^{-X}}}" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{Y&space;=mX&plus;c&space;}" title="\mathrm{Y =mX+c }" />
* We apply the straight line on the **Sigmoid** curve.
> <img src="https://latex.codecogs.com/svg.image?\mathrm{\sigma(Y)=\sigma(mX&plus;c)}" title="\mathrm{\sigma(Y)=\sigma(mX+c)}" />

* If our features are multiple then the equation would be 

> <img src="https://latex.codecogs.com/svg.image?Y=\beta&space;_0&plus;\beta_1x_1&plus;\beta_2x_2&plus;\beta_3x_3&plus;...&plus;\beta_nx_n" title="Y=\beta _0+\beta_1x_1+\beta_2x_2+\beta_3x_3+...+\beta_nx_n" />
 
* Or like this-

> <img src="https://latex.codecogs.com/svg.image?\mathrm{Y=W_nX_n&plus;W_{n-1}X_{n-1}&plus;...&plus;W_2X_2&plus;W_1X_1&plus;b}" title="\mathrm{Y=W_nX_n+W_{n-1}X_{n-1}+...+W_2X_2+W_1X_1+b}" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{\sigma\left&space;(&space;&space;W_nX_n&plus;W_{n-1}X_{n-1}&plus;...&plus;W_2X_2&plus;W_1X_1&plus;b\right&space;)}" title="\mathrm{\sigma\left ( W_nX_n+W_{n-1}X_{n-1}+...+W_2X_2+W_1X_1+b\right )}" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{Y=W^TX&plus;b}" title="\mathrm{Y=W^TX+b}" />
* This 'W' Transpose represents a matrix of all 'W' in above equation.
* After that this will pass through Sigmoid function and looks like -

> <img src="https://latex.codecogs.com/svg.image?\mathrm{\sigma&space;\left&space;(&space;&space;W^TX&plus;b\right&space;)}" title="\mathrm{\sigma \left ( W^TX+b\right )}" />

> <img src="https://latex.codecogs.com/svg.image?\mathrm{\widehat{Y}=\sigma&space;\left&space;(&space;&space;W^TX&plus;b\right&space;)}" title="\mathrm{\widehat{Y}=\sigma \left ( W^TX+b\right )}" />


>> <img src="https://latex.codecogs.com/svg.image?\mathrm{\textrm{If&space;}\widehat{Y}\geqslant&space;&space;0.5,&space;\textrm{then&space;1&space;}}" title="\mathrm{\textrm{If }\widehat{Y}\geqslant 0.5, \textrm{then 1 }}" />

>> <img src="https://latex.codecogs.com/svg.image?\mathrm{\textrm{If&space;}\widehat{Y}\leqslant&space;0.5,&space;\textrm{then&space;0&space;}}" title="\mathrm{\textrm{If }\widehat{Y}\leqslant 0.5, \textrm{then 0 }}" />



## Cost Function
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Cost function is error representation in ML
* Shows how our model is predicting compared to original given dataset.
* The terget is to minimum the cost or loss
* Cost of Linear regression is-

> <img src="https://latex.codecogs.com/svg.image?\textrm{Cost&space;for&space;Linear&space;Regression}=\frac{1}{m}\sum_{i=1}^{m}|Y_{i}-\widehat{Y_{i}}|" title="\textrm{Cost for Linear Regression}=\frac{1}{m}\sum_{i=1}^{m}|Y_{i}-\widehat{Y_{i}}|" />

>><img src="https://latex.codecogs.com/svg.image?Y=&space;Y_{pred}\textrm{&space;,&space;}&space;\widehat{Y}=Y_{actual}" title="Y= Y_{pred}\textrm{ , } \widehat{Y}=Y_{actual}" />

* If we use this cos function in Logistic regression we might end up in local minima not the global minima. As its cost function is calculated by gradient decent.

![minima](https://upload.wikimedia.org/wikipedia/commons/thumb/6/68/Extrema_example_original.svg/375px-Extrema_example_original.svg.png)


* So, Lost for Logistic is 
> <img src="https://latex.codecogs.com/svg.image?-\frac{1}{m}&space;\sum_{i=1}^{m}\left&space;[&space;\widehat{Y_i}&space;\log(Y_i)&plus;(1-\widehat{Y_i})\log(1-Y_i)&space;\right&space;]" title="-\frac{1}{m} \sum_{i=1}^{m}\left [ \widehat{Y_i} \log(Y_i)+(1-\widehat{Y_i})\log(1-Y_i) \right ]" />

>> <img src="https://latex.codecogs.com/svg.image?\textrm{Y&space;predict}=\mathrm{\sigma(W^{T}X&plus;b)}" title="\textrm{Y predict}=\mathrm{\sigma(W^{T}X+b)}" />



![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

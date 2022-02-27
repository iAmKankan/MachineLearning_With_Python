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
> ### _y = <a>&beta;<sub>0 + <a>&beta;<sub>1x  -------- (i)_

* And for logistic regression, we calculate probability. _i.e. **_y_** is the probability of a given variable **_x_** belonging to a certain class_. 
* Thus, it is obvious that the value of y should lie between **_0_** and **_1_**.
* But, when we use equation(i) to calculate probability, we would get values less than **0** as well as greater than **1**. Which doesn’t make any sense
* So, we need to use such an equation which always gives values between **0** and **1**, as we desire while calculating the probability.

### Sigmoid function 
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
<img src="https://user-images.githubusercontent.com/12748752/155903849-f8ab533c-74c3-440a-b5ea-920c0c7f4e04.PNG" width=50%>

<a><i><u> We use the sigmoid function as the underlying function in Logistic regression. Mathematically and graphically, it is shown as </u> </i></a>

**Why do we use the Sigmoid Function?**

1)	The sigmoid function’s range is bounded between 0 and 1. Thus it’s useful in calculating the probability for the  Logistic function.
2)	 It’s derivative is easy to calculate than other functions which is useful during gradient descent calculation.
3)	It is a simple way of introducing non-linearity to the model.

Although there are other functions as well, which can be used, but sigmoid is the most common function used for logistic regression. We will talk about the rest of the functions in the neural network section.

The logistic function is given as:

<img src="logistic_function.PNG" width="300">

Let’s see some manipulation with the logistic function: 

<img src="manip1.PNG" width="300">

We can see that the logit function is linear in terms with x.


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

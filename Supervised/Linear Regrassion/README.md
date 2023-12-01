## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Definition Of Linear Regression](#the-definition)
* [What is Regression](#what-is-regression)
* [Assumptions of Linear Regression](#assumptions-of-linear-regression)
  * [Multicollinearity](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Linear%20Regrassion/correlation.md)
  * [Linear and Additive](#linear-and-additive)
  * [Heteroscedasticity](#heteroscedasticity)
  * [Autocorrelation](#autocorrelation)
  * [Normal Distribution of error terms](#normal-distribution-of-error-terms)
* [Types of Linear Regression](#linear-regression-is-of-2-types)
  * [Simple Linear Regression](#1-simple-linear-regression)
  * [Multivariate Linear Regression](#2-multivariate-linear-regression)
* [Regularized Linear Models](https://github.com/iAmKankan/Regularization/blob/master/linear_regularization.md) 
  * [**_Ridge Regression_**](https://github.com/iAmKankan/Regularization/blob/master/linear_regularization.md)
  * [**_Lasso Regression_**](https://github.com/iAmKankan/Regularization/blob/master/linear_regularization.md)
  * [**_Elastic Net_**](https://github.com/iAmKankan/Regularization/blob/master/linear_regularization.md)
### [_Error_](#error-or-loss-or-cost)
  * [Residual Sum Of Squres(**RSS**)](#residual-sum-of-squres)
  * [Total Squired Error](#total-squired-error)
  * [Total varience in **Y**](#total-varience-in-y)
  * [ R Squared Error ( _**R <sup>2</sup>**_ ) or **Coefficient of Determination**](#r2-error-or-coefficient-of-determination)
  * [Adjusted R Squared Error (_**R <sup>2</sup>**_)](#adjusted-r2-error)

## Linear Regression
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
### The Definition
**Linear Regression tends to establish a relationship between _a dependent variable(Y)_ and _one or more independent variable(X)_ by finding the best fit of the straight line(regression line).**

<img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Linear_regression.svg" align=right width=30% />

* The equation for the Linear model is _**Y = mX+c**_, where _**m**_ is the slope and _**c**_ is the intercept
* Linear Regression When we want to predict real continuous values as an output
* There is no straight line that runs through all the data points. 
* So, the objective here is to fit the best fit of a straight line that will try to minimize the error between the expected and actual value.

### 🔲 What is Regression
[**Please follow the link**](https://github.com/iAmKankan/Statistics/blob/main/commonTerms.md#regression)

### 🔲 Assumptions of Linear Regression
Let’s look at the important assumptions in regression analysis-
  * There should be no [**correlation**](https://github.com/iAmKankan/Statistics/blob/main/commonTerms.md#correlation) between the **residual (error) terms**. Absence of this phenomenon is known as **_Autocorrelation_**.
  * The **_independent variables_** should not be **correlated**. Absence of this phenomenon is known as [**_Multicollinearity_**](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Linear%20Regrassion/correlation.md).
  * The error terms must have [constant variance](https://github.com/iAmKankan/Statistics/blob/main/measureofcentraltendency.md#constant-variance). This phenomenon is known as **Homoskedasticity**. The presence of non-constant variance is referred to **Heteroskedasticity**.
  * **The error terms must be [normally distributed](https://github.com/iAmKankan/Statistics/blob/main/probability/distributions.md#-what-is-a-normal-distribution)**.
  * There should be a **linear and additive relationship between dependent (response) variable and independent (predictor) variable(s)**. 
     * A linear relationship suggests that a change in response **_Y_** due to one unit change in **_X<sup>1</sup>_** is constant, regardless of the value of **_X<sup>1</sup>_**. 
     * An additive relationship suggests that the effect of **_X<sup>1</sup>_** on **_Y_** is independent of other variables.

### What if these assumptions get violated?

### Linear and Additive
* If you fit a linear model to a non-linear, non-additive data set, the regression algorithm would fail to capture the trend mathematically, thus resulting in an inefficient model. Also, this will result in erroneous predictions on an unseen data set.

#### How to check
* Look for **residual** vs **fitted** value plots.
*  Also, you can include polynomial terms (_X_, _X <sup>2</sup>_, _X <sup>3</sup>_ ) in your model to capture the non-linear effect.

### Multicollinearity
* [Please follow the link](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Linear%20Regrassion/correlation.md)
 ### Heteroscedasticity 
 * The presence of non-constant variance in the error terms results in heteroskedasticity.
 * Generally, non-constant variance arises in presence of outliers or extreme leverage values.
 * Look like, these values get too much weight, thereby disproportionately influences the model’s performance. 
 * When this phenomenon occurs, the confidence interval for out of sample prediction tends to be unrealistically wide or narrow.

#### How to check
* You can look at residual vs fitted values plot.
*  If heteroskedasticity exists, the plot would exhibit a funnel shape pattern (shown in next section). 
*  Also, you can use Breusch-Pagan / Cook – Weisberg test or White general test to detect this phenomenon.
 ### Autocorrelation 
 * It's refers to a perticular data where the error term of one time period is correlated to the error term of anothether time period. 
 * This is very common to time series data analysis.
 #### How to check
 * Durbin – Watson (DW) statistic. 
    *  It must lie between 0 and 4.
    *  If DW = 2, implies no autocorrelation, 
    *  0 < DW < 2 implies positive autocorrelation 
    *  2 < DW < 4 indicates negative autocorrelation
 *  Also, you can see residual vs time plot and look for the seasonal or correlated pattern in residual values.
  
### Normal Distribution of error terms
* If the error terms are non- normally distributed, confidence intervals may become too wide or narrow.
* Once confidence interval becomes unstable, it leads to difficulty in estimating coefficients based on minimization of least squares.
* Presence of non – normal distribution suggests that there are a few unusual data points which must be studied closely to make a better model.

#### How to check: 
* You can look at QQ plot (shown below). 
* You can also perform statistical tests of normality such as Kolmogorov-Smirnov test, Shapiro-Wilk test.


## Types of Linear Regression
Linear Regression is of 2 types
 1) **Simple Linear Regression** 
 2) **Multivariate Linear Regression**
    
     
### 1. Simple Linear Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{Y=a&plus;bX}\&space;\&space;\&space;\&space;\&space;Where\&space;\begin{cases}\mathit{Y&space;=&space;Dependent\&space;Variable&space;}&space;\\\mathit{a&space;=&space;Y\&space;intercept&space;}&space;\\\mathit{b&space;=&space;Slope\&space;of\&space;the\&space;line}&space;\\\mathit{X&space;=&space;Independent\&space;variable}&space;\\\end{cases}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{Y=a+bX}\ \ \ \ \ Where\ \begin{cases}\mathit{Y = Dependent\ Variable } \\\mathit{a = Y\ intercept } \\\mathit{b = Slope\ of\ the\ line} \\\mathit{X = Independent\ variable} \\\end{cases}}" />


* It contains only one input variable. Only one regression line.
* $\large \textrm{Y intercept (a)}$: is the value of the Dependent variable(y) when the value of the indipendent variable is zero(0). This is the point at which the line cuts the **y-axis**.
* $\large \textrm{Slope(b)}$: is the change in the Dependent Variable(y) for a unit increase in the indipendent variable. It is the tangent of  the angle made by the line with the **x-axis**.

$${\color{Purple} \mathbf{b=\dfrac{y_2-y_1}{x_2-x_1}}} \[\textit{Later in Calculus}\]$$

### 2. Multivariate Linear Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{Y=\beta&space;_0&plus;\beta_1x_1&plus;\beta_2x_2&plus;\beta_3x_3&plus;...&plus;\beta_nx_n}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{Y=\beta _0+\beta_1x_1+\beta_2x_2+\beta_3x_3+...+\beta_nx_n}}" />

* Here we need to find out all the <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{\beta}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{\beta}}" align="center"/> coefficients.
* It means the <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{\beta}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{\beta}}" align="center"/> is creating some kind of relationship or slope in respect to the output variable.
* Findout the relationshiop between <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{\beta}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{\beta}}" align="center"/> and the output variables.

<img src="https://user-images.githubusercontent.com/12748752/176559935-2b014f87-62d2-4333-92c4-cd61feac96ff.png" width=50%/>

### 🔲 Error or Loss or Cost
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
### ⚫ _Residual Sum Of Squres_
#### The Error is the _distance_ from the _bestfit line_ to _each observation_. Our aim is to minimize the error. 
The **_Deviation_** or the **_Error_** is also called **_Residual_**.

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{Residual&space;=&space;(Y_p-Y_a)}}&space;\&space;\&space;{\color{Purple}\begin{cases}&space;p=predicted\\a=actual\end{cases}&space;}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{Residual = (Y_p-Y_a)}} \ \ {\color{Purple}\begin{cases} p=predicted\\a=actual\end{cases} }" />

#### Sum of all Errors
<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{AllResidual=&space;\sum(Y_p-Y_a)}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{AllResidual= \sum(Y_p-Y_a)}}" />

#### In order to eliminate the nagative from _Y actuals_ (_-Y<sub>a</sub>_), we take the squre (<sup>2</sup>) of the whole residuals and it becomes- 
> #### _Residual Sum Of Squres(RSS)_ = _Ordinary least squares(OLS)_ = _Error function_ = _Loss Function_.

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{ResidualSumOfSqures=&space;\sum(Y_p-Y_a)^2}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{ResidualSumOfSqures= \sum(Y_p-Y_a)^2}}" />


#### Now we have to take the minimum of all errors. That's will give us the beest fit line.
Inorder to fing out the minimum of a function we need to use **first order derivation** and **second order derivation** to find out the **minima** and **maxima**.

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{ResidualSumOfSqures&space;=&space;\left&space;(min&space;\sum&space;(Y_p-Y_a)^2\right&space;)}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{ResidualSumOfSqures = \left (min \sum (Y_p-Y_a)^2\right )}}" />

#### _Best-fit-line_ we need to find out when we findout the '_a_' and the '_b_' that's the line which is the min error.

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{ResidualSumOfSqures&space;=&space;\left&space;(min&space;\sum&space;(Y_p-Y_a)^2\right&space;)}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{ResidualSumOfSqures = \left (min \sum (Y_p-Y_a)^2\right )}}" />

#### _This function is Parabola or Convex shaped curve_
If we replace the above function with this <img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{Y=X^2}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{Y=X^2}}" align="center"/>

* For **X= -1,-2,0,1,2** result will be **1,4,0,1,4** if we ploted over a chart it will be like- 
<img src="https://user-images.githubusercontent.com/12748752/176536026-6ce5fc99-c3c9-4c06-99e4-4b0cf5a1d5fa.jpg" width=50%>


> ### Inorder to findout the minimum error we use gradient descent
> #### The learning rate is represented by alpha <img src="https://latex.codecogs.com/svg.image?\alpha" title="\alpha" />

[Linear Regression Simulator](https://www.mladdict.com/linear-regression-simulator)


### ⚫ _Total Squired Error_
<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{SE_{Line}&space;=(Y_1-(bX_1&plus;a))^2&plus;(Y_2-(bX_2&plus;a))^2&plus;...&plus;(Y_n-(bX_n&plus;a))^2}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{SE_{Line} =(Y_1-(bX_1+a))^2+(Y_2-(bX_2+a))^2+...+(Y_n-(bX_n+a))^2}}" />


### ⚫ _Total varience in Y_
Is the Squared Error of the mean, The mean of all **Y** is represented by <img src="https://latex.codecogs.com/svg.image?\overline{Y}" title="\overline{Y}" />

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{SE_{\overline{Y}}&space;=(Y_1-\overline{Y})^2&plus;(Y_2-\overline{Y})^2&plus;...&plus;(Y_n-\overline{Y})^2}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{SE_{\overline{Y}} =(Y_1-\overline{Y})^2+(Y_2-\overline{Y})^2+...+(Y_n-\overline{Y})^2}}" />
 
#### What % of the variation is _NOT_ Described by the variation in _X_ or by the Regression line = <img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{\frac{SE_{Line}&space;}{SE_{\overline{Y}}}}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{\frac{SE_{Line} }{SE_{\overline{Y}}}}}" align="center"/>


### ⚫ _R<sup>2</sup> Error_ or _Coefficient of Determination_
#### Coefficient of Determination = What % of the variation is acctually Described by the vasriation in _X_ or by the Regression line = <img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{1-\frac{SE_{Line}&space;}{SE_{\overline{Y}}}}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{1-\frac{SE_{Line} }{SE_{\overline{Y}}}}}" align="center" />

* If <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{SE_{Line}}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{SE_{Line}}}" align="center" /> is very small then we can say that the regression line is good fit and the <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{R^2}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{R^2}}" align="center"/> is close to **_1_**.
* If <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{SE_{Line}}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{SE_{Line}}}" align="center" />   is large then  the <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{R^2}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{R^2}}" align="center"/> is close to **_0_** and the regression line is loosely fit.


![error](https://user-images.githubusercontent.com/12748752/127488864-8d0310bd-02a5-4bab-8ea6-5140917eca64.png)

### ⚫ _Adjusted R<sup>2</sup> Error_
* It is possible to get <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{R^2}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{R^2}}" align="center"/>  value < **_0_**(**-ve**)
   * When the the regression line is not better than the average line or Total varience in **Y**
* If we add independent features the value of <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{R^2}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{R^2}}" align="center"/>  is improves by decresing the value of <img src="https://latex.codecogs.com/svg.image?{\color{Purple}&space;\mathbf{SE_{Line}}}" title="https://latex.codecogs.com/svg.image?{\color{Purple} \mathbf{SE_{Line}}}" align="center" />. But the features may not to correlated  to the output variable **Y**.
* So, it is not penalising the new added features.
* In  _Adjusted R<sup>2</sup> Error_ it penalizes attributes that are not correlated with **Y**.

<img src="https://latex.codecogs.com/svg.image?\large&space;{\color{Purple}&space;\mathbf{R^2\&space;adjusted=&space;1-}\mathbf{\frac{(1-R^2)(N-1)}{N-p-1}}\&space;\&space;\&space;\&space;\&space;Where\&space;\begin{cases}\mathit{R^2=\&space;Sample\&space;R-square&space;}&space;\\\mathit{p=\&space;Number\&space;of\&space;Predictors&space;}&space;\\\mathit{N=\&space;Total\&space;sample\&space;size}&space;\\\end{cases}}" title="https://latex.codecogs.com/svg.image?\large {\color{Purple} \mathbf{R^2\ adjusted= 1-}\mathbf{\frac{(1-R^2)(N-1)}{N-p-1}}\ \ \ \ \ Where\ \begin{cases}\mathit{R^2=\ Sample\ R-square } \\\mathit{p=\ Number\ of\ Predictors } \\\mathit{N=\ Total\ sample\ size} \\\end{cases}}" />

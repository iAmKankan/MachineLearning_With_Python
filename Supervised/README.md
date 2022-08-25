## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Supervised Learning](#supervised-learning) 
* [Supervised Learning Catagories](#supervised-learning-catagories)   
    * [Linear Regression](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Linear%20Regrassion#readme)
    * [Logistic Regression](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Logistic%20Regrassion#readme)
    * [Decision Tree](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Decision%20Tree#readme)
    * [Random Forest]()
    * [Naive Bayes]()
    * [SVM](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/SVM#readme)

### Supervised Learning
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<img src="https://user-images.githubusercontent.com/12748752/186329450-e7e071a7-f1fc-46dc-825d-03305c3e9c89.png" width=70%/>

### Regression
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

#### Fitting the Data
Add supporting information to the text, including equations, images, and hyperlinks.

Let's try fitting the data with **polynomial regression**. We'll use the _MATLAB polyfit_ function to get the coefficients.

**We will see later how this relates perfectly with our linear regression procedure**.

#### The fit equations are:

$$\large{\color{Purple}
\begin{cases}
linear & y = w_1x+w_0  \\
quadratic & y = w_2x^2+w_1x+w_0 \\
cubic  & y = w_3x^3+w_2x^2+w_1x+w_0 \\
\end{cases}
}
$$

#### Example:
<img src="https://user-images.githubusercontent.com/12748752/186338649-5d77b044-8c6c-4ffe-a525-debcdbfa101d.png" width=70%/>
---
* Supervised Learning is where you have a input variable(x) and a output variable(y) and you use a mapping function from the input to the output
* It is called supervised because the process of an algorithm training fom the dataset can be thought as a teacher supervising the learning process. 

 <img src="https://latex.codecogs.com/svg.image?Y=F(X)" title="Y=F(X)" />
 
### Data point
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
<img src="https://user-images.githubusercontent.com/12748752/186367469-db591c5e-8fde-48d4-b5a8-35566cb138af.png" width=30%/> <img src="https://user-images.githubusercontent.com/12748752/186380825-d6cd3822-0512-4db3-a2f9-b85231395a19.png" width=30%/>

We start with the case where there is a single input and a single output 
* $\large{\color{Purple} (x^{(i)}, y^{(i)})} : i^{th} \textit{ example of (input, output) set.}$
*  $\large{\color{Purple}m}$ : Number of examples or data points.
* We assume that there are **51** pairs of data points.
#### Hypothesis
The general univariate linear regression problem
We now introduce our model hypothesis Linear Model-

$$ \large{\color{Purple} \hat{y}= h(x)=w_{0}+ w_{1}x} $$
   

* $\large{\color{Purple} w_0, w_1}$ are parameters and there are infinite possibilities. Which do we choose?
* For this we defined a cost function $\large{\color{Purple} J=\frac{1}{2m} \sum_{i}(y^{(i)}- \hat{y}^{(i)})^2}$ 
    * Notice that no line is going to fit all of this perfectly so the difference between the points $\large{\color{Purple}y}$ and the pont resides on the regression line $\large{\color{Purple}\hat{y}}$ is the loss.  

#### How would we achieve our optimal $\large{\color{Purple} w}$ ?.
   * So we say that the optimal $\large{\color{Purple} w}$ (so you can now notice it has now become optimization problem) is the one **_which minimizes this net cost function_**. 
   * So the $\large{\color{Purple} w}$ that we get at the end of the process will be called **_Least Square Coefficient_**
   * This **_fit_** is called **_Least Square fit_** and the **_cost function_** is called **_Least Mean Squre (LMS)_**

### Measuring the _Fit_
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
<img src="https://user-images.githubusercontent.com/12748752/186551372-28265384-b462-4ebb-ba0d-d412af31aade.png" width=40%/>

**Mean Square Error:**

$$\large{\color{Purple} J=\frac{1}{2m} \sum_{i}(y^{(i)}- \hat{y}^{(i)})^2}$$

So this is one measure of how good the **fit** is. Sometimes this is not a good enough, sometimes we just get a large value of **J** and we don’t know whether this is a good fit or not. 


#### Varience 

$$\large{\color{Purple}\sum^{m}_{i=1} (y_i-\bar{y})^2} {\color{Cyan}\textrm{(SST) Sum Square Total}}$$

What does total variance mean? Before we even had a model there was some amount of **variation** in the data, and this term actually calculates the total amount of variance in the data **before we even had a model**.

Amount of varience present in the data

#### Error

$$\large{\color{Purple}\sum^{m}_{i=1} (y_i-\hat{y_i})^2} {\color{Cyan}\textrm{(SSE) Sum Square Error}}$$

Here y<sub>i</sub> is the **Ground Truth** and the &hat; y<sub>i</sub> is the prediction or Hypothesis or Model.
#### Varience in Prediction

$$\large{\color{Purple}\sum^{m}_{i=1} (\hat{y_i} - \bar{y})^2} {\color{Cyan}\textrm{(SSR) Sum Square Regression}}$$

Amount of varience captured by the model.

#### $\large R^2$ Error

$$\large{\color{Purple}\mathbf{R^2} = \frac{\textrm{SSR}}{\textrm{SST}} = \frac{\textit{Amount of varience captured by the Model}}{\textit{Amount of varience present in Data}} }$$


Typically we would like one number which lie between **0** and **1**. So we want to normalize this. You have a number, you would like to non-dimensionalize it, normalize it with respect to some denominator, so that you get an idea between **0** and **1**.

$$\large{\color{Purple} \mathbf{R^2 \in \Bigl[0, 1 \Bigl] } }  \normalsize{\color{Cyan} \begin{cases} 0 &= Very\ Bad\ fit \\
1 &= Very\ Good \ fit
\end{cases}}
$$ 


### Supervised Learning Catagories - Based on Types
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
<img src="https://user-images.githubusercontent.com/12748752/141359379-bbb6102c-ae37-477d-a5a1-a6b1cedd3295.png" height=100%/>

### Machine Learning Catagories - Based on Outliers handling
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
<img src="https://user-images.githubusercontent.com/12748752/146688585-e2ecc295-c3e0-4ea8-acb1-ad03a8ec8ce6.png" width=100% />

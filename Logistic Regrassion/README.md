## Logistic Regression
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
## Index






### Difference between Linear Regression and Logistic Regression
||Y|X|
|:---:|:---:|:---:|
|Linear Regression|<img src="https://latex.codecogs.com/svg.image?\mathrm{-\infty&space;\textbf{To}&space;&plus;\infty" title="\mathrm{-\infty \textbf{To} +\infty" />|<img src="https://latex.codecogs.com/svg.image?\mathrm{-\infty&space;\textbf{To}&space;&plus;\infty" title="\mathrm{-\infty \textbf{To} +\infty" />|
|Logistic Regression|_0 or 1_|<img src="https://latex.codecogs.com/svg.image?\mathrm{-\infty&space;\textbf{To}&space;&plus;\infty" title="\mathrm{-\infty \textbf{To} +\infty" />|



![](https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png =250x250)



### Definition
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Logestic Regression is a binary classifier that classify your data as a linear separation boundary.
* But unlike Linear Regression the result cann't be infered by drawing a single regression line, like below-
![linear_logis](https://user-images.githubusercontent.com/12748752/136411478-043f0eb2-e6ef-43d5-9e34-dc1d02f073cc.png){:width=50%}





* **The logistic regression technique involves the dependent variable, which can be represented in the binary (0 or 1, true or false, yes or no) values.**
* Which means that the outcome could only be in either one form of two.
* For example, it can be utilized when we need to find the probability of a **successful** or **fail event**.

* **Logistic Regression is a Machine Learning algorithm which is used for the classification problems.**
* it is a predictive analysis algorithm and based on the concept of probability. 

* We can call a Logistic Regression a Linear Regression model but the Logistic Regression uses a more complex cost function, this cost function can be defined as the **‘Sigmoid function’** or also known as the **‘logistic function’** instead of a linear function.**

* The hypothesis of logistic regression tends it to limit the cost function between 0 and 1. Therefore linear functions fail to represent it as it can have a value greater than 1 or less than 0 which is not possible as per the hypothesis of logistic regression.
    
    ![](https://miro.medium.com/max/279/1*GnceHPIeThNShGSmYzE4eA.png)


**Logistic regression** is the appropriate regression analysis to conduct when the dependent variable is dichotomous (binary). Like all regression analyses, the logistic regression is a predictive analysis. Logistic regression is used to describe data and to explain the relationship between one dependent binary variable and one or more nominal, ordinal, interval or ratio-level independent variables.

Logistic Regression is used when the dependent variable (target) is categorical.

For example:

- To predict whether an email is spam (1) or (0).
- Whether online transaction is fraudulent (1) or not (0).
- Whether the tumor is malignant (1) or not (0).

In other words the dependant variable (output) for logistic regression model may be described as:

![Logistic Regression Output](../images/logistic_regression/output.svg)

![Logistic Regression](https://cdn-images-1.medium.com/max/1600/1*4G0gsu92rPhN-co9pv1P5A@2x.png)

![Logistic Regression](https://cdn-images-1.medium.com/max/1200/1*KRhpHnucyX9Y5PMdjGvVFA.png)

## Training Set

Training set is an input data where for every predefined set of features _x_ we have a correct classification _y_.

![Training Set](../images/logistic_regression/training-set-1.svg)

_m_ - number of training set examples.

![Training Set](../images/logistic_regression/training-set-2.svg)

For convenience of notation, define:

![x-zero](../images/logistic_regression/x-0.svg)

![Logistic Regression Output](../images/logistic_regression/output.svg)

## Hypothesis (the Model)

The equation that gets features and parameters as an input and predicts the value as an output (i.e. predict if the email is spam or not based on some email characteristics).

![Hypothesis](../images/logistic_regression/hypothesis-1.svg)

Where _g()_ is a **sigmoid function**.

![Sigmoid](../images/logistic_regression/sigmoid.svg)

![Sigmoid](https://upload.wikimedia.org/wikipedia/commons/8/88/Logistic-curve.svg)

Now we my write down the hypothesis as follows:

![Hypothesis](../images/logistic_regression/hypothesis-2.svg)

![Predict 0](../images/logistic_regression/predict-0.svg)

![Predict 1](../images/logistic_regression/predict-1.svg)

## Cost Function

Function that shows how accurate the predictions of the hypothesis are with current set of parameters.

![Cost Function](../images/logistic_regression/cost-function-1.svg)

![Cost Function](../images/logistic_regression/cost-function-4.svg)

![Cost Function](../images/logistic_regression/cost-function-2.svg)

Cost function may be simplified to the following one-liner:

![Cost Function](../images/logistic_regression/cost-function-3.svg)

## Batch Gradient Descent

Gradient descent is an iterative optimization algorithm for finding the minimum of a cost function described above. To find a local minimum of a function using gradient descent, one takes steps proportional to the negative of the gradient (or approximate gradient) of the function at the current point.

Picture below illustrates the steps we take going down of the hill to find local minimum.

![Gradient Descent](https://cdn-images-1.medium.com/max/1600/1*f9a162GhpMbiTVTAua_lLQ.png)

The direction of the step is defined by derivative of the cost function in current point.

![Gradient Descent](https://cdn-images-1.medium.com/max/1600/0*rBQI7uBhBKE8KT-X.png)

Once we decided what direction we need to go we need to decide what the size of the step we need to take.

![Gradient Descent](https://cdn-images-1.medium.com/max/1600/0*QwE8M4MupSdqA3M4.png)

We need to simultaneously update ![Theta](../images/logistic_regression/theta-j.svg) for _j = 0, 1, ..., n_

![Gradient Descent](../images/logistic_regression/gradient-descent-1.svg)

![Gradient Descent](../images/logistic_regression/gradient-descent-2.svg)

![alpha](../images/logistic_regression/alpha.svg) - the learning rate, the constant that defines the size of the gradient descent step

![x-i-j](../images/logistic_regression/x-i-j.svg) - _j<sup>th</sup>_ feature value of the _i<sup>th</sup>_ training example

![x-i](../images/logistic_regression/x-i.svg) - input (features) of _i<sup>th</sup>_ training example

_y<sup>i</sup>_ - output of _i<sup>th</sup>_ training example

_m_ - number of training examples

_n_ - number of features

> When we use term "batch" for gradient descent it means that each step of gradient descent uses **all** the training examples (as you might see from the formula above).

## Multi-class Classification (One-vs-All)

Very often we need to do not just binary (0/1) classification but rather multi-class ones, like:

- Weather: Sunny, Cloudy, Rain, Snow
- Email tagging: Work, Friends, Family

To handle these type of issues we may train a logistic regression classifier ![Multi-class classifier](../images/logistic_regression/multi-class-classifier.svg) several times for each class _i_ to predict the probability that _y = i_.

![One-vs-All](https://i.stack.imgur.com/zKpJy.jpg)

## Regularization

### Overfitting Problem

If we have too many features, the learned hypothesis may fit the **training** set very well:

![overfitting](../images/logistic_regression/overfitting-1.svg)

**But** it may fail to generalize to **new** examples (let's say predict prices on new example of detecting if new messages are spam).

![overfitting](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/fittings.jpg)

### Solution to Overfitting

Here are couple of options that may be addressed:

- Reduce the number of features
    - Manually select which features to keep
    - Model selection algorithm
- Regularization
    - Keep all the features, but reduce magnitude/values of model parameters (thetas).
    - Works well when we have a lot of features, each of which contributes a bit to predicting _y_.

Regularization works by adding regularization parameter to the **cost function**:

![Cost Function](../images/logistic_regression/cost-function-with-regularization.svg)

![regularization parameter](../images/logistic_regression/lambda.svg) - regularization parameter

> Note that you should not regularize the parameter ![theta zero](../images/logistic_regression/theta-0.svg).

In this case the **gradient descent** formula will look like the following:

![Gradient Descent](../images/logistic_regression/gradient-descent-3.svg)

## References

- [Machine Learning on Coursera](https://www.coursera.org/learn/machine-learning)
- [Sigmoid Function on Wikipedia](https://en.wikipedia.org/wiki/Sigmoid_function)
- [Gradient Descent on Wikipedia](https://en.wikipedia.org/wiki/Gradient_descent)
- [Gradient Descent by Suryansh S.](https://hackernoon.com/gradient-descent-aynk-7cbe95a778da)
- [Gradient Descent by Niklas Donges](https://towardsdatascience.com/gradient-descent-in-a-nutshell-eaf8c18212f0)
- [One vs All on Stackexchange](https://stats.stackexchange.com/questions/318520/many-binary-classifiers-vs-single-multiclass-classifier)
- [Logistic Regression by Rohan Kapur](https://ayearofai.com/rohan-1-when-would-i-even-use-a-quadratic-equation-in-the-real-world-13f379edab3b)
- [Overfitting on GeeksForGeeks](https://www.geeksforgeeks.org/underfitting-and-overfitting-in-machine-learning/)

## Index
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Data Split with `train_test_split()`](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/training_performance-evaluation/data_split.md)
  * [Regression notebook](https://nbviewer.org/github/iAmKankan/MachineLearning_With_Python/blob/master/training_performance-evaluation/train-test-Regression.ipynb)
* [Linear Regression Errors](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Linear%20Regrassion#error-or-loss-or-cost)

## ML Data flow During training
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

<img src="https://user-images.githubusercontent.com/12748752/176580015-39aad2f3-e47d-4a6c-99d7-f5a958d78f68.png" width=100% />

<p align="center"><ins><i><b>ML Data flow During training</b></i></ins>.</p>

![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

## Performance Measures
![dark](https://user-images.githubusercontent.com/12748752/141935752-90492d2e-7904-4f9f-a5a1-c4e59ddc3a33.png)
Evaluating a classifier is often significantly trickier than evaluating a regressor. There are many performance measures available.

### 1) Measuring Accuracy Using Cross-Validation
![light](https://user-images.githubusercontent.com/12748752/141935760-406edb8f-cb9b-4e30-9b69-9153b52c28b4.png)
In machine learning, we couldn’t fit the model on the training data and can’t say that the model will work accurately for the real data. For this, we must assure that our model got the correct patterns from the data, and it is not getting up too much noise. For this purpose, we use the **cross-validation** technique.

> #### _Cross-validation_ is a technique in which we train our model using the _subset of the data-set_ and then _evaluate using the complementary subset_ of the data-set.
The three steps involved in cross-validation are as follows :
* Reserve some portion of sample data-set.
* Using the rest data-set train the model.
* Test the model using the reserve portion of the data-set
#### Methods of Cross Validation
#### 1) Validation
In this method, we perform **training on the 50%** of the given data-set and rest **50% is used for the testing** purpose.

#### 2) LOOCV (Leave One Out Cross Validation)
In this method, we perform training on the whole data-set but leaves only one data-point of the available data-set and then iterates for each data-point. It has some advantages as well as disadvantages also.

#### 3)K-Fold Cross Validation
In this method, we split the data-set into **k** number of subsets(known as **folds**) then we perform **training** on the all the subsets but leave one(**k-1**) subset for the **evaluation of the trained model**. In this method, we iterate **k** times with a different subset reserved for testing purpose each time.

> ### Scikit-Learn’s **cross-validation** features expect a _utility function_ (_**greater is better**_) rather than a _cost function_ (_**lower is better**_), so the scoring function is actually the opposite of the MSE (i.e., a negative value), _which is why the preceding code computes -scores before calculating the square root_.

## Model Performance Evaluation - Classification
#### 1) Confusion Matrix:
#### 2) Gain and Lift Charts
#### 3) Lift Chart
#### 4) K-S Chart 
#### 5) ROC Chart
#### 6) Area Under the Curve (AUC)


## 1) Confusion Matrix:
![dark](https://user-images.githubusercontent.com/12748752/141935752-90492d2e-7904-4f9f-a5a1-c4e59ddc3a33.png)
<img src="https://user-images.githubusercontent.com/12748752/168250710-596bf1a2-5d86-464d-b07f-70264ce4a3c3.png" width=30%/>
#### <ins><i>Confusion Matrix</i></ins>
An NxN table that aggregates a classification model's correct and incorrect guesses. One axis of a confusion matrix is the label that the model predicted, and the other axis is the ground truth. N represents the number of classes. For example, N=2 for a binary classification model. For example, here is a sample confusion matrix for a binary classification model:

### ***Classification reports***
- Precision Score
- Recall Score
- F1 Score
- Support
- ConfusionMatrix

### Evaluating Binary Classifier Predictions
![light](https://user-images.githubusercontent.com/12748752/141935760-406edb8f-cb9b-4e30-9b69-9153b52c28b4.png)
When it comes to evaluating a Binary Classifier, **Accuracy** is a well-known performance metric that is used to tell a strong classification model from one that is weak. Accuracy is, simply put, the total proportion of observations that have been correctly predicted. There are four (4) main components that comprise the mathematical formula for calculating Accuracy, viz. **TP**, **TN**, **FP**, **FN**, and these components grant us the ability to explore other ML Model Evaluation Metrics. The formula for calculating accuracy is as follows:

#### The formula: 
$$\large \mathbf{{\color{Purple} Accuracy= \frac{TP+TN}{TP+FP+TN+FN}}}$$

### Precision Score
This refers to the proportion (total number) of all observations that have been predicted to belong to the positive class and are actually positive. The formula for Precision Evaluation Metric is as follows:
$$\large \mathbf{{\color{Purple} Precision= \frac{TP}{TP+FP} }}$$

### Recall
This is the proportion of observation predicted to belong to the positive class, that truly belongs to the positive class. It indirectly tells us the model’s ability to randomly identify an observation that belongs to the positive class. The formula for Recall is as follows:
$$\large \mathbf{{\color{Purple} Recall= \frac{TP}{TP+FN} }}$$
### F1 Score.
This is an averaging Evaluation Metric that is used to generate a ratio. The F1 Score is also known as the Harmonic Mean of the precision and recall Evaluation Metrics. This Evaluation Metric is a measure of overall correctness that our model has achieved in a positive prediction environment-
i.e., Of all observations that our model has labeled as positive, how many of these observations are actually positive. The formula for the F1 Score

$$\large {\color{Purple} 
\begin{matrix}
\textbf{F1  Score} & = & \frac{2}{\huge{\frac{1}{Precision}+\frac{1}{Recall}}} \\
\\
& = & \huge{\frac{2(Precision\ * \ Recall)}{{Precision}+{Recall}}  }
\end{matrix}}
$$

## Evaluating Multiclass Classifier Predictions
![dark](https://user-images.githubusercontent.com/12748752/141935752-90492d2e-7904-4f9f-a5a1-c4e59ddc3a33.png)

## Model Performance Evaluation - Regression
![dark](https://user-images.githubusercontent.com/12748752/141935752-90492d2e-7904-4f9f-a5a1-c4e59ddc3a33.png)
Accuracy (e.g. **classification accuracy**) is a measure for **classification**, not **regression**.
> #### We don't calculate accuracy for a regression model.The **skill** or **performance** of a regression model must be reported as an **_Error_** in those predictions.

> ### There is no correct value for MSE. Simply put, the _lower the value the better_ and **0** means the model is perfect. 
 
This makes sense if you think about it. If you are predicting a numeric value like a height or a dollar amount, you don’t want to know if the model predicted the value exactly (this might be intractably difficult in practice); instead, we want to know how close the predictions were to the expected values.

Error addresses exactly this and summarizes on _average how close predictions were to their expected values_.

There are **three error metrics** that are commonly used for evaluating and reporting the performance of a regression model; they are:
1) **_Mean Squared Error (MSE)_**.
2) **_Root Mean Squared Error (RMSE)_**.
3) **_Mean Absolute Error (MAE)_**.

There are many other metrics for regression, although these are the most commonly used. [Scikit-Learn API: Regression Metrics](https://scikit-learn.org/stable/modules/classes.html#regression-metrics).

## Metrics for Regression
![light](https://user-images.githubusercontent.com/12748752/141935760-406edb8f-cb9b-4e30-9b69-9153b52c28b4.png)

### **_Mean Squared Error (MSE)_**
It is also an important loss function for algorithms fit or optimized using the least squares framing of a regression problem. Here “least squares” refers to minimizing the mean squared error between predictions and expected values.

The **MSE** is calculated as the **mean** or **average** of the **squared differences** between predicted and expected target values in a dataset.
$$\large {\color{Purple} \mathbf{MSE=} \mathbf{\frac{1}{n}\sum_{i=1}^{n} \left ( Y_i - \hat{Y_i} \right )^2} }$$


### **_Root Mean Squared Error_**
The **Root Mean Squared Error**, or **RMSE**, is an extension of the mean squared error.

Importantly, the square root of the error is calculated, which means that the units of the RMSE are the same as the original units of the target value that is being predicted.

For example, if your target variable has the units “dollars,” then the RMSE error score will also have the unit “dollars” and not “squared dollars” like the MSE.

As such, it may be common to use MSE loss to train a regression predictive model, and to use RMSE to evaluate and report its performance.

The RMSE can be calculated as follows:

$$\large {\color{Purple} \mathbf{RMSE=} \mathbf{\sqrt{\frac{1}{n}\sum_{i=1}^{n} \left ( Y_i - \hat{Y_i} \right )^2} } }$$

$$\large {\color{Purple}\mathbf{or}}$$

$$\large {\color{Purple} \mathbf{RMSE=} \mathbf{\sqrt{MSE} } }$$

Where y_i is the i’th expected value in the dataset, yhat_i is the i’th predicted value, and sqrt() is the square root function.

We can restate the RMSE in terms of the MSE as:


Note that the RMSE cannot be calculated as the average of the square root of the mean squared error values. This is a common error made by beginners and is an example of Jensen’s inequality.

You may recall that the square root is the inverse of the square operation. MSE uses the square operation to remove the sign of each error value and to punish large errors. The square root reverses this operation, although it ensures that the result remains positive.

The root mean squared error between your expected and predicted values can be calculated using the mean_squared_error() function from the scikit-learn library.

By default, the function calculates the MSE, but we can configure it to calculate the square root of the MSE by setting the “squared” argument to False.

The function takes a one-dimensional array or list of expected values and predicted values and returns the mean squared error value.

### Mean Absolute Error
Mean Absolute Error, or MAE, is a popular metric because, like RMSE, the units of the error score match the units of the target value that is being predicted.

Unlike the RMSE, the changes in MAE are linear and therefore intuitive.

That is, MSE and RMSE punish larger errors more than smaller errors, inflating or magnifying the mean error score. This is due to the square of the error value. The MAE does not give more or less weight to different types of errors and instead the scores increase linearly with increases in error.

As its name suggests, the MAE score is calculated as the average of the absolute error values. Absolute or abs() is a mathematical function that simply makes a number positive. Therefore, the difference between an expected and predicted value may be positive or negative and is forced to be positive when calculating the MAE.

The MAE can be calculated as follows:

$$\large {\color{Purple} \mathbf{MAE=} \mathbf{\frac{1}{n}\sum_{i=1}^{n} \left | Y_i - \hat{Y_i} \right |} }$$

Where y_i is the i’th expected value in the dataset, yhat_i is the i’th predicted value and abs() is the absolute function.

We can create a plot to get a feeling for how the change in prediction error impacts the MAE.

The example below gives a small contrived dataset of all 1.0 values and predictions that range from perfect (1.0) to wrong (0.0) by 0.1 increments. The absolute error between each prediction and expected value is calculated and plotted to show the linear increase in error.

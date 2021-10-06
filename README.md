### Index 
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
*  [What is Machine Learning](#what-is-machine-learning)
*  [Lifecycle of ML](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/ML_lifecycle.md#lifecycle-of-ml)
   * Data Acquisition
   * [Data Preparation/ Data Preprocessing](https://github.com/iAmKankan/Data-Gathering-And-Preprocessing#readme)
   * Hypothesis & Modeling
   * Evaluation & Interpretation
   * Deployment
   * Operation & Optimization
* [Supervised Learning](#supervised-learning)   
  * **Statistical Concept based Algos**
    * [Linear Regression](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Linear%20Regrassion#linear-regression)
    * [Logistic Regression]()
  * **Information Theory Concept**
    * [Decision Tree]()
    * [Random Forest]()
  * **Basian Statistics**
    * [Naive Bayes]()
  * **Pure Mathemetical optimisation model**
    * [SVM]()
* [Terminologies](#terminologies)
   * [Bias and Varience](#bias-and-varience)
     * [Regularization]
     * [Boosting]
     * [Bagging]
   * [Overfitting And Underfitting](#overfitting-and-underfitting)


## What is Machine Learning
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* Machine learning focuses on the development of computer programs that can access data and use it to learn for themselves.

###  [Lifecycle of ML](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/ML_lifecycle.md#lifecycle-of-ml)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

* Data Acquisition
* [Data Preparation/ Data Preprocessing](https://github.com/iAmKankan/Data-Gathering-And-Preprocessing#readme)
* Hypothesis & Modeling
* Evaluation & Interpretation
* Deployment
* Operation & Optimization

 
### Supervised Learning
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

* Supervised Learning is where you have a input variable(x) and a output variable(y) and you use a mapping function from the input to the output


* It is called supervised because the process of an algorithm training fom the dataset can be thought as a teacher supervising the learning process. 


 <img src="https://latex.codecogs.com/svg.image?Y=F(X)" title="Y=F(X)" />



![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<img src="https://latex.codecogs.com/svg.image?\begin{matrix}\textbf{ML&space;algorithms&space;Sensitive&space;to&space;outliers}&space;\\\textit{1.&space;Linear&space;Regression}\\\textit{2.&space;Logistic&space;Regression}\\\textit{3.&space;Support&space;Vector&space;Machine}\\\textit{4.&space;K-&space;Nearest&space;Neighbors}\\\textit{5.&space;K-Means&space;Clustering}\\\textit{6.&space;Hierarchical&space;Clustering}\\\textit{7.&space;Principal&space;Component&space;Analysis}&space;\\\end{matrix}" title="\begin{matrix}\textbf{ML algorithms Sensitive to outliers} \\\textit{1. Linear Regression}\\\textit{2. Logistic Regression}\\\textit{3. Support Vector Machine}\\\textit{4. K- Nearest Neighbors}\\\textit{5. K-Means Clustering}\\\textit{6. Hierarchical Clustering}\\\textit{7. Principal Component Analysis} \\\end{matrix}" />
<img src="https://latex.codecogs.com/svg.image?\begin{matrix}\textbf{ML&space;algorithms&space;Not&space;Sensitive&space;to&space;outliers}&space;\\\textit{1.&space;Decision&space;Tree}\\\textit{2.&space;Random&space;Forest}\\\textit{3.&space;XGBoost}\\\textit{4.&space;AdaBoost}\\\textit{5.&space;Naive&space;Bayes}\\\end{matrix}" title="\begin{matrix}\textbf{ML algorithms Not Sensitive to outliers} \\\textit{1. Decision Tree}\\\textit{2. Random Forest}\\\textit{3. XGBoost}\\\textit{4. AdaBoost}\\\textit{5. Naive Bayes}\\\end{matrix}" />

![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)


## Terminologies
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

### Bias and Varience
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Suppose we have some observations(data) and they are split into train data and test data.
* **In the first scenario**, like Linear Regression we draw a regression line through the training observations and obhously that straight line cann't cover each and every observation.
* The minimum of the sum of the squre of the difference between the line and each observation is the error.
* That scenario is called Bias.
* **In the second scenario**, we draw a squiggly line which connects each and every training observations.
* Now the error is zero.
* But when we run test data, the error for train data and the test data of 1st scenario is almost the same. The error for train data which is zero but the test data of 2nd scenario is different. Here difference between the train and the test is a consequence of variance.
* The 1st scenario is having high Bias but it has low varience because the sum of squre is similer for the different data sets and it performence is consistent.
* Because the squiggly line is fitted in train set but not in test set we say it is **Overfit** and the performance is not consistence.
* In machine learning, the ideal algorithm has low bias and can accurately model the true relationship and it has low variability, by producing consistent predictions across different datasets.
* Three commonly used methods for finding the sweet spot between simple and complicated models are:
  * Regularization.
  * Boosting.
  * Bagging.
### Overfitting And Underfitting
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Overfitting and Underfitting is direct related to Bias and Varience.
* In simple words-
  * **Overfitting** means you have trained your model havely that it gives good accuracy with training datya but failing miserably with test data.
  * **Underfit** means you have not trained your data good enough to get a decent accuracy.


![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
 

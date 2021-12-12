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
* [Supervised Learning](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised) 
  * **Statistical Concept based Algos**
    * [Linear Regression](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Linear%20Regrassion#readme)
    * [Logistic Regression](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Logistic%20Regrassion#readme)
  * **Information Theory Concept**
    * [Decision Tree](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Decision%20Tree#readme)
    * [Random Forest]()
  * **Basian Statistics**
    * [Naive Bayes]()
  * **Pure Mathemetical optimisation model**
    * [SVM]()
* [Unsupervised Learning](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/unsupervised/README.md)
   * Clustering
      * K-Means
      * DBSCAN
      * Hierarchical Cluster Analysis (HCA)
   * Anomaly detection and novelty detection
      * One-class SVM
      * Isolation Forest
  * Visualization and dimensionality reduction
     * Principal Component Analysis (PCA)
     * Kernel PCA
     * Locally-Linear Embedding (LLE)
     * t-distributed Stochastic Neighbor Embedding (t-SNE)
  * Association rule learning
     * Apriori
     * Eclat
* [Terminologies](#terminologies)
   * [Bias and Varience](#bias-and-varience)
     * [Regularization]()
     * [Boosting]()
     * [Bagging]()
   * [Overfitting And Underfitting](#overfitting-and-underfitting)
   * [MODEL INTERPRETATION](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/README.md#model-interpretation)
      * [WHITE BOX Models](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/README.md#white-box-models)
      * [BLACK BOX Models](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/README.md#black-box-models)
   * [Curse of Dimensionlity](https://github.com/iAmKankan/Data-Gathering-And-Preprocessing/blob/main/README.md#curse-of-dimentionlity)
   * [Linear and Non-Linear Classifications](#linear-classification-vs-non-linear-classification)


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

 

## Terminologies
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

### Bias and Varience
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Suppose we have some observations(data) and they are split into train data and test data.
> #### In the first scenario
* Like Linear Regression we draw a regression line through the training observations and obhously that straight line cann't cover each and every observation.
* The minimum of the sum of the squre of the difference between the line and each observation is the error.
* That scenario is called Bias.
> #### In the second scenario
* We draw a squiggly line which connects each and every training observations.
* Now the error is zero.
* But when we run test data, the error for train data and the test data of 1st scenario is almost the same. The error for train data which is zero but the test data of 2nd scenario is different. Here difference between the train and the test is a consequence of variance.
* The 1st scenario is having high Bias but it has low varience because the sum of squre is similer for the different data sets and it performence is consistent.
* Because the squiggly line is fitted in train set but not in test set we say it is **Overfit** and the performance is not consistence.
* In machine learning, the ideal algorithm has low bias and can accurately model the true relationship and it has low variability, by producing consistent predictions across different datasets.
* Three commonly used methods for finding the sweet spot between simple and complicated models are:
  * [**Regularization.**](https://github.com/iAmKankan/Regularization/blob/master/README.md)
  * [**Boosting.**](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Ensemble-Learning_and_Randon-Forest/boosting.md)
  * [**Bagging.**](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Ensemble-Learning_and_Randon-Forest/Voting_Bagging_Pasting_OoBEvalution.md)
### Overfitting And Underfitting
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Overfitting and Underfitting is direct related to Bias and Varience.
* In simple words-
  * **Overfitting** means you have trained your model havely that it gives good accuracy with training datya but failing miserably with test data.
  * **Underfit** means you have not trained your data good enough to get a decent accuracy.

## MODEL INTERPRETATION
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* `Decision Trees` are intuitive, and their decisions are easy to interpret. 
* Such models are often called white box models. 
* `Random Forests` or `neural networks` are generally considered black box models. 
* They make great predictions, and you can easily check the calculations that they performed to make these predictions; nevertheless, it is usually hard to explain in simple terms why the predictions were made. 
* For example, if a neural network says that a particular person appears on a picture, it is hard to know what contributed to this prediction: did the model recognize that person’s eyes? Their mouth? Their nose? Their shoes? Or even the couch that they were sitting on? Conversely, Decision Trees provide nice, simple classification rules that can even be applied manually if need be (e.g., for flower classification).
### WHITE BOX Models
* Interpretable models are models who explain themselves, for instance from a decision tree you can easily extract decision rules. 
   * **Linear Regression**
   * **Logistic Regression**
   * **Desission Tree**
* Banking sector and Healthcare sector it is very common.
### BLACK BOX Models
* Every other model than interpretable models are fall under this catagory
  * **Deep Learning** models are fully Black-Box models.
  *  **Random Forest** is fully Black-Box model.
  
  
  

### Linear Classification Vs Non-Linear Classification
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

#### Linear Classifier
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Let’s say we have data from two classes (o and  χ ) distributed as shown in the figure below. 
* To discriminate the two classes, one can draw an arbitrary line, s.t. all the ‘o’ are on one side of the line and  χ ’s on the other side of the line. 
* These two classes are called linearly-separable.

<img src="https://user-images.githubusercontent.com/12748752/144843896-495dcb21-0fda-4887-ad92-63581c467e52.gif" width=20%/>

* However, there are infinite number of lines that can be drawn to discriminate two separable classes, as shown below
<img src="https://user-images.githubusercontent.com/12748752/144843889-fc4494a5-7493-4220-99a5-094c7a6ff107.png" width=20%/>

* How you approximate the exact location of this discriminating line (or plane or hyperplane) depends on the type of a classifier called linear classifier.
* Some examples of linear classifier are: `Linear Discriminant Classifier`, `Naive Bayes`, `Logistic Regression`, `Perceptron`, `SVM (with linear kernel)`.


#### Non-Linear Classifier
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Let’s consider the famous XOR problem. An XOR’s truth table and the data distribution is shown below.
* In this situation, there is no way that a straight line can be drawn to discriminate the two classes (0 and 1)

<img src="https://user-images.githubusercontent.com/12748752/144843899-ea16eeac-2329-4664-8912-60f26d9cfaff.gif"/>



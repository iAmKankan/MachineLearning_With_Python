## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Voting, Bagging-Pasting, Out of the Box Evalution](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Ensemble-Learning_and_Randon-Forest/Voting_Bagging_Pasting_OoBEvalution.md)
* [Ensemble Learning and Random Forests](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Ensemble-Learning_and_Randon-Forest/RandomForest.md)

### ⬛ $\Large {\color{blue}\underline{\mathcal{Ensemble\ Learning\ and\ Random\ Forests:}}}$
### 🔲 $\large {\color{Purple}\underline{\textrm{Wisdom of the Crowd:}}}$
Suppose you pose a complex question to thousands of **random people**, then **aggregate** their answers. In many cases you will find that this **aggregated answer** is better than an expert’s answer. This is called the **wisdom of the crowd**. 

Similarly, if you **aggregate** the predictions of **a group of predictors** (such as **classifiers** or **regressors**), you will often get better **predictions** than with the best **individual predictor**. 
* Here **A group of predictors** is called an **_Ensemble_**,
* Thus, this technique is called _**Ensemble Learning**_, and
* **An Ensemble Learning algorithm** is called an **_Ensemble method_**.
  
### 🔲 $\large {\color{Purple}\underline{\textrm{Ensemble Learning:}}}$

**Ensemble methods** combine the predictions of <ins>several base estimators</ins> **built with a given learning algorithm** in order to improve <ins>generalizability</ins> / <ins>robustness</ins> over a **single estimator**.

**Ensemble methods** work **best** when the <ins>predictors are as independent as possible from one another</ins>. **One way to get diverse classifiers** is to train them using very <ins>different algorithms.</ins>. This increases the chance that they will make very different types of **errors**, <ins>improving the ensemble’s accuracy</ins>.

Two very famous examples of ensemble methods are **gradient-boosted trees** and **random forests**.

More generally, ensemble models can be applied to **any base learner** beyond trees, in **averaging methods** such as **Bagging methods**, **model stacking** or **Voting** or in **boosting** as **AdaBoost**.

* $\large {\color{Purple}\underline{\textrm{Base learners}}}$ are the first level of an ensemble learning architecture and each one of them is **trained to make individual predictions**. 
* $\large {\color{Purple}\underline{\textrm{Meta learners}}}$ on the other hand are in the second level and they are **trained on the output of the base learners**. 

### Types of Ensemble Methods
There are various types of ensemble learning methods, including:

1. **Bagging (Bootstrap Aggregating):** This method involves training multiple models on random subsets of the training data. The predictions from the individual models are then combined, typically by averaging.
2. **Committe Machine:**
3. **Stacking:** This method involves using the predictions from one set of models as input features for another model. The final prediction is made by the second-level model.
4. **Boosting:** This method involves training a sequence of models, where each subsequent model focuses on the errors made by the previous model. The predictions are combined using a weighted voting scheme.


### ♠️  $\large {\color{purple}1.\underline{\textrm{Bagging}}}$
Bootstrap Aggregating, also known as bagging, is a machine learning ensemble meta-algorithm designed to improve the stability and accuracy of machine learning algorithms used in statistical classification and regression. It decreases the variance and helps to avoid overfitting. It is usually applied to decision tree methods. Bagging is a special case of the model averaging approach. 


### ♠️ $\large{\color{purple}4.\underline{\textrm{Boosting:}}}$
Boosting is a method used in machine learning to <ins><b>reduce errors</b></ins> in <ins>predictive data analysis</ins>. 

Boosting is an **ensemble** modeling technique that attempts to build a strong classifier from the **number of weak classifiers**. It is done by building a model by using weak models in series. 

### $\large{\color{purple}\underline{\textrm{ADA Boost}}}$

1. **Firstly**, a model is built from the training data.
2. Then the **second model** is built which tries to **correct the errors** present in the **first model**.
3. This procedure is continued and <ins>models are added</ins> until either <ins><b>the complete training data set is predicted correctly</b></ins> or <ins><b>the maximum number of models are added</b></ins>. 

### $\large{\color{purple}\underline{\textrm{Mathametical Expression}}}$

$$\Large{\color{Purple}C_{(m-1)}(x)= \alpha_{1}k_{1}(x)+\alpha_{2}k_{2}(x)+\cdots+\alpha_{m-1}k_{m-1}(x) }$$

* I am going to denote by $\large{\color{purple}C}$ of $\large{\color{purple}x}$ of $\large{\color{purple}(m-1)^{th}}$ stage classifier,
* That is obtained by basically adding the outputs of all this individual classifies. E.g $\large{\color{purple}k_1, k_2 ,\cdots, k_{m-1}}$
* $\large{\color{purple}\alpha_1, \alpha_2 ,\cdots, \alpha_{m-1}}$ these are the weights.
* $\large{\color{purple}k_1}$ is a classifier that I added in the <ins><b>first stage</b></ins>.
* $\large{\color{purple}k_2}$ is the classifier added in the <ins><b>second stage</b></ins> and so on so forth .
* $\large{\color{purple}k_{m-1}}$ is a classifier added in the <ins><b>(m-1) stage</b></ins> okay.

### $\large{\color{purple}\underline{\textrm{Error or Loss}}}$

Now, I am going to take this above equation and look at the **residual error**, as I can consider this as a **prediction problem**. Look at the **residual error** of the predictor and then <ins><b>train the below classifier</b></ins> $\large{\color{purple}k_{m}}$ to **minimize** the **residual error**.

$$\Large{\color{Purple}C_{(m)}(x)= C_{(m-1)}(x) + \alpha_{m}k_{m}(x)}$$


#### So what will be $\large{\color{purple}\alpha_m}$ here? 
$\Large Answer:$ Its just selecting classifiers.

* So I can just take the **residual error** of $\large{\color{purple}c_{m-1}}$ and then use that to train $\large{\color{purple} k_{m}(x)}$ and then add it here.
* In fact $\large{\color{purple}\alpha_{m} }$ can be **1**. it can be one does not matter because the $\large{\color{purple}k_m(x)}$ will actually align itself in the direction of the residual so I can just add it here so it is fine.
* And it is actually a good way to do it if you are doing regression let that make sense and I can take this as they can take the residual error and then train my $\large{\color{purple}k_m}$ to actually go in the direction of the residual.


So, I can actually do this, so you can get a boosting like algorithm for regression just by training it along the direction of a residual right, but when I am doing classification that is not necessarily the right thing to do so people come up with different kinds of loss functions and then they try to improve the classification, so the **loss function** we look at is the **exponential loss**.


### <ins>Exponential Loss</ins>:

$$\Huge{\color{Purple}e^{-y_{i}f(x_i)}}$$

### <ins>Exponential Loss on our equation</ins>:

$$\Large{\color{Purple}E = \sum_{i=1}^{N} e^{-y_{i}(C_{(m-1)}(x) + \alpha_{m}k_{m}(x))}}$$

$$\Large{\color{purple}\normalsize{\textrm{ We got the above by expanded- }} \large \sum_{i=1}^{N} e^{-y_{i}f(x_i)}}$$


This was not the way **ADA BOOST** was originally derived, **ADA BOOST** was derived in a completely different way and later on about five years after they publish **ADA BOOST** they kind of discovered the connection between this kind of <ins><b>forward stage ways modeling</b></ins> or <ins><b>additive modeling</b></ins> and <ins><b>exponential loss</b></ins> they said okay, I can do forward stage wise modeling with and **exponential loss** function I end up with **ADA BOOST** that connection was discovered five years later. But now almost always people except in the theory community, in the machine learning community is always introduced like this.

Lets  re write

$$\Large{\color{Purple}\begin{matrix}
E &=& \sum\limits_{i=1}^{N} e^{-y_{i}(C_{(m-1)}(x) + \alpha_{m}k_{m}(x))} \\
&=& \sum\limits_{i=1}^{N} e^{-y_{i} \alpha_m k_m (x_i)} \ \ ; \normalsize\textrm{ Where } \Large w_i^{(m)} = e^{-y_i C_{m-1}(x_i)}\\
\end{matrix}}$$

* The weight $\large{\color{purple}w}$ of the $\large{\color{purple}i^{th}}$ data point, at the $\large{\color{purple}m^{th}}$ stage is essentially e power minus y sub i C sub m minus one of x sub i or $\large{\color{purple}e^{-y_i C_{m-1}(x_i)}}$ .
* So what is this  $\large{\color{purple}e^{-y_i C_{m-1}(x_i)}}$ ? It is a loss I have incurred on that point $\large{\color{purple}x_i}$ up till the $\large{\color{purple}m-1}$ stage.

I am going to break that sum up into two components


$$\Large{\color{Purple}E = \underbrace{\sum w_i^{(m)} e^{-\alpha_m}}_{y_i=k_m(x_i)} + \underbrace{\sum w_i^{(m)} e^{\alpha_m}}\_{y_i \neq k_m(x_i)} }$$

* $\large{\color{purple} \sum w_i^{(m)} e^{-\alpha_m}}$ ; When it is correctly classified.
* $\large{\color{purple} \sum w_i^{(m)} e^{\alpha_m}}$ ; When it is wrongly classified.
 






![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)


### Description of the Technique

Suppose a set D of d tuples, at each iteration i, a training set Di of d tuples is selected via row sampling with a replacement method (i.e., there can be repetitive elements from different d tuples) from D (i.e., bootstrap). Then a classifier model Mi is learned for each training set D < i. Each classifier Mi returns its class prediction. The bagged classifier M* counts the votes and assigns the class with the most votes to X (unknown sample).


### Random Forest
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* In _Random Forest_, we train a group of Decision Tree classifiers, each on a different random subset of the training set.
* To make predictions, we obtain the predictions of all the individual trees, then predict the class that gets the most votes.



* Random Forest is an ensemble machine learning algorithm that follows the bagging technique. 
* The base estimators in the random forest are decision trees. 
* Random forest randomly selects a set of features that are used to decide the best split at each node of the decision tree.

  1. Random subsets are created from the original dataset (bootstrapping).
  2. At each node in the decision tree, only a random set of features are considered to decide the best split.
  3. A decision tree model is fitted on each of the subsets.
  4. The final prediction is calculated by averaging the predictions from all decision trees.

* Builds multiple decision trees and merges them togather.
* More accurate and stable prediction.
* Random decision forest correct for the dicision trees' habit of overfitting to their training set.
* Training with the "bagging" method. This based on the idea that the combination of the learning model increases the overall result.
* if the learning dataset is huge then a single decision tree results a 

### References:
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

* Hands-On Machine Learning with Scikit-Learn Keras and TensorFlow Concepts Tools and Techniques to Build Intelligent Systems by Aurélien Géron, 2nd Edition
* [Scikit Learn](https://scikit-learn.org/stable/modules/ensemble.html#voting-classifier)
* IITM - Bala

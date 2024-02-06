## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Randomforest,Extra Forest, Feature inportance Notebook](https://nbviewer.org/github/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Ensemble-Learning_and_Randon-Forest/Random_Forest.ipynb)

### Bagging of Trees
* So now we know that **trees** are great candidates for **boosting** as well if you are using **gradient boosting**.
* However, **trees** are great candidates for **bagging** as well as right.
* **What is the important property in bagging that we talked about?** What does **bagging** help us **reduce variance**.
* You can show that the **reduction in variance is highest if the classifiers that you are building or not correlated**.

 So I am building many, many classifiers, and the classifiers are predicting the **same output**. So if the classifier parameter set I am estimating, or somehow if we can make them uncorrelated, then the reduction in variance is maximum it kind of intuitive right. If the classifiers are very correlated, there is no point, they are not different classifiers right, and they will give me the same output, so the variance will be high.

 So if you can somehow make the **classifiers** **uncorrelated**, then the **reduction in variance is high**. 
 * And if you think about what we are doing with **bagging**, we are taking one data set and we are sampling with replacement from that.
 * So the probability of the trees that you are generating being correlated is rather high.
 * So it can become up with some way to reduce the correlation between the trees you are constructing .
  
### While doing Bagging the goal is to reduce the correlation between the trees:

I am going to be doing bagging right, but the goal is to reduce the correlation between trees. The people who came up with the random forest had a very simple idea for doing this right, and you start doing bagging as you would normally do okay. 
* So you have your data set, then you create a bag by sampling with replacement from that data.
* Now, when you start building the tree on this data set, so what do you do at every node right, sample some P features from your feature set, and use P for the regular feature description right..










### Random Forests
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* **In **_Random Forest_**, we train a group of Decision Tree classifiers, each on a different random subset of the training set.**
* To make predictions, we obtain the predictions of all the individual trees, then predict the class that gets the most **_votes_**.
* Random Forest is an **ensemble** of _**Decision Trees**_, generally trained via the **bagging method** (or sometimes pasting), typically with **`max_samples`** set to the size of the training set. 
* Instead of building a _`BaggingClassifier`_ and passing it a DecisionTreeClassifier, you can instead use the _`RandomForestClassifier`_ class, which is more convenient and optimized for `Decision Trees` (similarly, there is a _`RandomForestRegressor`_ class for regression tasks).
* With a few exceptions, a `RandomForestClassifier` has all the hyperparameters of a `DecisionTreeClassifier` (to control how trees are grown), plus all the hyperparameters of a `BaggingClassifier` to control the ensemble itself.
* The Random Forest algorithm introduces extra randomness when growing trees; instead of searching for the _very best feature_ when splitting a node (in Decission Tree), _it searches for the best feature among a random subset of features._
* The algorithm results in greater tree diversity, which (again) trades a **_higher bias for a lower variance_**, generally yielding an overall better model.

### Extra-Trees or _`Extremely Randomized Trees ensemble`_
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* In a Random Forest, at each node only a **_random subset of the features is considered for splitting_**.
* It would make trees even more random by also using _**random thresholds for each feature**_ rather than searching for the [best possible thresholds](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised/Decision%20Tree#how-the-algorithm-works--) (like regular Decision Trees do).
* A forest of such extremely random trees is called an **_Extremely Randomized Trees ensemble_** (or Extra-Trees for short). 
* Once again, this technique trades more bias for a lower variance. 
* It also makes Extra-Trees much faster to train than regular Random Forests, because finding the best possible threshold for each feature at every node is one of the most time-consuming tasks of growing a tree.

* Extra-Trees classifier using Scikit-Learn’s **_`ExtraTreesClassifier`_** class.

> #### It is hard to tell in advance whether a `RandomForestClassifier` will perform better or worse than an `ExtraTreesClassifier`. Generally, the only way to know is to try both and compare them using `cross-validation` (tuning the `hyperparameters` using `grid search`).


### Feature Importance 
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Yet another great quality of Random Forests is that they make it easy to measure the relative importance of each feature. 
* `Scikit-Learn` measures a feature’s importance by looking at **_how much the tree nodes that use that feature reduce impurity on average_** (across all trees in the forest).
* More precisely, it is a _weighted average_, where each node’s weight is equal to the number of training samples that are associated with it.
* `Scikit-Learn` computes this score automatically for each feature after training, then it scales the results so that the sum of all importances is equal to 1. 
* You can access the result using the ***feature_importances_*** variable.



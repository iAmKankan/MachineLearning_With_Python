## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
 
## _Ensemble Learning_ and _Random Forests_ 
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* Suppose you pose a complex question to thousands of random people, then aggregate their answers. In many cases you will find that this aggregated answer is better than an expert’s answer. 
* This is called the _`wisdom of the crowd`_. 
* Similarly, if you aggregate the predictions of a group of predictors (such as **classifiers** or **regressors**), you will often get better predictions than with the best individual predictor. 
* _A group of predictors_ is called an **_ensemble_**; thus, this _technique_ is called _**Ensemble Learning**_, and _an Ensemble Learning algorithm_ is called an **_Ensemble method_**.


> #### Ensemble methods work best when the predictors are as _independent_ from one another as possible. One way to get diverse classifiers is to train them using _very different algorithms_. _This increases the chance that they will make very different types of errors, improving the ensemble’s accuracy_.

### _Voting Classifiers_
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Suppose we have trained a few classifiers, each one achieving about 80% accuracy.Like- a Logistic Regression classifier, an SVM classifier, a Random Forest classifier, a K-Nearest Neighbors classifier, and many more.
* A very simple way to create an even better classifier is to aggregate the predictions of each classifier and predict the class that gets the most votes. 
* This majority-vote classifier is called a _**hard voting classifier**_
* **Voting Classifier** Voting classifier has two types. **Hard Voting Classifier** and **Soft Voting Classifier**.
* Voating Classicier works in **Ensemble** or **RandomForest** or in **Deep Learning**.
* Suppose in Random Forest classifier has two classes ***0*** and ***1*** and we have four Decision Trees **[D1,D2,D3,D4]** which gives the results- **[0, 1, 1, 1]**.
    * For **Hard Voting Classifier** the result would be ***1*** since the maximum models gives the output.
    * For **Soft Voting Classifier** it gives us the probablity. As shown in the below table, It take sthe higher probability scores.
    
| Decission Tree |Class **1** |Class **0** |
|----|-------|-------|
| D1 | .95 | .05 |
| D2 | .86 | .14 |
| D3 | .7 | .3 |
| D4 | .6 | .4 |


* The result is (.95+.86+.7+.6)/4 = 0.7775




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

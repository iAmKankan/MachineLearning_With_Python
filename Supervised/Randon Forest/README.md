# Random Forest

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
<img src="randomforest2.png?raw=true">

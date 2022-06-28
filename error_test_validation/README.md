## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
## The Introduction
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
**Supervised machine learning** is about creating models that precisely map the given **inputs** (**independent variables**, or **predictors**) to the given **outputs** (**dependent variables**, or **responses**).

How you measure the **precision** of your model depends on the type of a problem you’re trying to solve- 
  * **Regression analysis**, you typically use the **_coefficient of determination_**, **_root-mean-square error_**, **_mean absolute error_** or **_similar quantities_**. 
  * **Classification** problems, you often apply **_accuracy_**, **_precision_**, **_recall_**, **_F1 score_** and related indicators.

## Training, Validation and Test Sets
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
Splitting the dataset is essential for an **unbiased evaluation** of prediction performance or it can leads to the data leackage(**Data leakage** in machine learning happens when the data that we are used to training a machine learning algorithm is having the information which the model is trying to predict). In most cases, it’s enough to split your dataset randomly into **three** subsets:
1) **The training set** is applied to **train** or **fit** our model. For example, you use the training set to find the **optimal weights** or **coefficients**, for **_linear regression_**, **_logistic regression_** or **_neural networks_**.
2) **The validation set** is used for _unbiased model evaluation_ during **_hyperparameter tuning_**. For example, when you want to find the **optimal number of neurons in a neural network** or the **best kernel for a support vector machine**, you experiment with different values. For each considered setting of **hyperparameters**, you **fit** the model with the **training set** and assess its **performance with the validation set**.
   * GridSearchCV
   * RandomSearchCV
   * Cross Validation.etc.
3) **The test set** is needed for an _unbiased evaluation_ of the **final model** or to perform the model prediction.

> In less complex cases, when you don’t have to tune hyperparameters, it’s okay to work with only the training and test sets.

## Underfitting and Overfitting
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
Splitting a dataset might also be important for **detecting** if our model suffers from one of two very common problems, called **underfitting** and **overfitting**:
* **Underfitting** is usually the consequence of a model being unable to encapsulate the relations among data. For example, this can happen when trying to represent **nonlinear relations** with a **linear model**. Underfitted models will likely have poor performance with both training and test sets.
* **Overfitting** usually takes place when a model has an **excessively complex structure** and learns both the existing relations among **data** and **noise**. Such models often have bad **generalization capabilities**. _Although they work well with training data_, _they usually yield poor performance with unseen (test) data_.




## Cross-Validation
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Determining the best way to partition, train, validate, and test data is important





## References
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [DataRobo](https://www.datarobot.com/wiki/)
* [Real Python](https://realpython.com/train-test-split-python-data/)
* [Towards Data Science](https://towardsdatascience.com/understanding-train-test-split-scikit-learn-python-ea676d5e3d1)

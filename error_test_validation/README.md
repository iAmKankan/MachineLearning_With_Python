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

![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

## Application of train_test_split()
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
> #### Import Packages:
You need to import **_`train_test_split()`_** and NumPy before you can use them, so you can start with the import statements:

```Python
 import numpy as np
 from sklearn.model_selection import train_test_split
```
> #### Data Prep:
To get your data, you use **`arange()`**, which is very convenient for generating arrays based on _numerical ranges_. You also use **`.reshape()`** to modify the shape of the array returned by **`arange()`** and get a two-dimensional data structure.
```Python
x = np.arange(1, 25).reshape(12, 2)
y = np.array([0, 1, 1, 0, 1, 0, 0, 1, 1, 0, 1, 0])
```
> #### The Split:
With **_`train_test_split()`_**, you need to provide the sequences that you want to split as well as any optional arguments. It returns a list of **NumPy arrays**, other sequences, or **SciPy** sparse matrices if appropriate:

> #### Parameters
```Python
sklearn.model_selection.train_test_split(*arrays, **options) -> list
```
In supervised machine learning applications, you’ll typically work with two such sequences:
* A **two-dimensional** array with the inputs (**x**)
* A **one-dimensional** array with the outputs (**y**)

`options` are the optional keyword arguments that you can use to get desired behavior:
* **_train_size_** is the number that defines the size of the training set. If you provide a float, then it must be between 0.0 and 1.0 and will define the share of the dataset used for testing. If you provide an int, then it will represent the total number of the training samples. The default value is None.
* **_test_size_** is the number that defines the size of the test set. It’s very similar to train_size. You should provide either train_size or test_size. If neither is given, then the default share of the dataset that will be used for testing is 0.25, or 25 percent.
* **_random_state_** is the object that controls randomization during splitting. It can be either an int or an instance of RandomState. The default value is None.
* **_shuffle_** is the Boolean object (True by default) that determines whether to shuffle the dataset before applying the split.
* **_stratify_** is an array-like object that, if not None, determines how to use a stratified split.

Now it’s time to try data splitting! You’ll start by creating a simple dataset to work with. The dataset will contain the inputs in the **two-dimensional** array **x** and outputs in the **one-dimensional** array **y**:


```Python 
x_train, x_test, y_train, y_test = train_test_split(x, y)
```
> #### Output
 Given two sequences, like **x** and **y** here, ***`train_test_split()`*** performs the split and returns four sequences (in this case **NumPy** arrays) in this order:

1) **_x_train_**: The training part of the first sequence (x)
2) **_x_test_**: The test part of the first sequence (x)
3) **_y_train_**: The training part of the second sequence (y)
4) **_y_test_**: The test part of the second sequence (y)













## Cross-Validation
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Determining the best way to partition, train, validate, and test data is important





## References
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [DataRobo](https://www.datarobot.com/wiki/)
* [Real Python](https://realpython.com/train-test-split-python-data/)
* [Towards Data Science](https://towardsdatascience.com/understanding-train-test-split-scikit-learn-python-ea676d5e3d1)

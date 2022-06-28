![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

## Application of _`train_test_split()`_:
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

## Syntax for the function _`train_test_split()`_
```Python
sklearn.model_selection.train_test_split(*arrays, **options) -> list
```

### Parameters to the function e.g _`*arrays`_
_`*arrays`_ is the sequence of **lists**, **NumPy arrays**, **pandas DataFrames** or similar **array-like objects** that hold the data you want to split. All these objects together make up the dataset and must be of the same length.

In supervised machine learning applications, you’ll typically work with two such _sequences_:
* A **two-dimensional** array with the **_inputs_** (**x**)
* A **one-dimensional** array with the **_outputs_** (**y**)

### Parameters to the function e.g _`**options`_
_`**options`_ are the _optional keyword arguments_ that you can use to get desired behavior:
* **_train_size_** is the number that defines the size of the training set. If you provide a float, then it must be between 0.0 and 1.0 and will define the share of the dataset used for testing. If you provide an int, then it will represent the total number of the training samples. The default value is None.
* **_test_size_** is the number that defines the size of the test set. It’s very similar to train_size. You should provide either train_size or test_size. If neither is given, then the default share of the dataset that will be used for testing is 0.25, or 25 percent.
* **_random_state_** is the object that controls randomization during splitting. It can be either an int or an instance of RandomState. The default value is None.
* **_shuffle_** is the Boolean object (True by default) that determines whether to shuffle the dataset before applying the split.
* **_stratify_** is an array-like object that, if not None, determines how to use a stratified split.


## Essential packages to be import:
Numpy library needs to be import along with the  _`train_test_split`_ package
```Python
 import numpy as np
 from sklearn.model_selection import train_test_split
```
### The function:
```Python 
x_train, x_test, y_train, y_test = train_test_split(x, y)
```
### Output Variables
Given two sequences, like **x** and **y** here, ***`train_test_split()`*** performs the split and returns four sequences (in this case **NumPy** arrays) in this order:

1) **_x_train_**: The training part of the first sequence (x)
2) **_x_test_**: The test part of the first sequence (x)
3) **_y_train_**: The training part of the second sequence (y)
4) **_y_test_**: The test part of the second sequence (y)

### The randomness
The dataset splitting is **random** by default. The result differs each time you run the function. However, this often isn’t what you want.

Sometimes, to make your tests reproducible, you need a random split with the same output for each function call. You can do that with the parameter random_state. The value of random_state isn’t important—it can be any non-negative integer. You could use an instance of numpy.random.RandomState instead, but that is a more complex approach.

In the previous example, you used a dataset with twelve observations (rows) and got a training sample with nine rows and a test sample with three rows. That’s because you didn’t specify the desired size of the training and test sets. By default, 25 percent of samples are assigned to the test set. This ratio is generally fine for many applications, but it’s not always what you need.

Typically, you’ll want to define the size of the test (or training) set explicitly, and sometimes you’ll even want to experiment with different values. You can do that with the parameters train_size or test_size.

Modify the code so you can choose the size of the test set and get a reproducible result:

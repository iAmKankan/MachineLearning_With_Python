![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

## Application of _`train_test_split()`_:
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

## Syntax of _`train_test_split()`_
![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

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


## Essential packages to import:
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

## The parameters for _`train_test_split()`_ (_`**options`_)
![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

### The randomness
The dataset splitting is **random** by default. The result differs each time you run the function.

Sometimes, to make your tests **reproducible**, you need a random split with the same output for each function call. You can do that with the parameter **_`random_state`_**. The value of **_`random_state`_** isn’t important—it can be any non-negative integer. You could use an instance of **_`numpy.random.RandomState`_** instead, but that is a more complex approach.

The samples of the dataset are shuffled randomly and then split into the training and test sets according to the size you defined.

### The size of _train data_ or _test data_
By default, **25 percent** of samples are assigned to the **test set**. This ratio is generally fine for many applications, but it’s not always what you need.

Typically, you’ll want to define the size of the **test** (or **training**) set explicitly, and sometimes you’ll even want to experiment with different values. You can do that with the parameters **_`train_size`_** or **_`test_size`_**.

### Statify
Suppose **y** has _six zeros_ and _six ones_. However, the _**test set**_ has _three zeros_ out of _four items_. If you want to (approximately) keep the proportion of **y** values through the **training** and **test** sets, then pass **_`stratify=y`_**. This will enable stratified splitting:

Now **_`y_train`_** and **_`y_test`_** have the same ratio of zeros and ones as the original **y** array.

**Stratified** splits are desirable in some cases, like when you’re classifying an **_imbalanced dataset_**, a dataset with a significant difference in the number of samples that belong to distinct classes.

### Sheffle
We can turn off data shuffling and random split with **_`shuffle=False`_**:  
> No **shuffling**. No **randomness**.

As you can see when **_`shuffle=False`_** then no matter what we set for **_`random_state`_**, it will <ins>linearly divide the data into **train** and **test** data</ins>.

> ### Why _`random_state=42`_?
You may have seen multiple times that most commonly **42** is used for **`random_state`**. Is there any reason for that? And the answer is NO. Python has used **42** as **`random_state`** in their documentation for example and many people have copied from the example code snippet, some people may have used it subconsciously and some may have used it lazily. So there is no particular reason for using 42 as random_state number and you are free to use any number you want.

Does this random seed has to be 42? Not really. It can be any number. To be specific, 42 have nothing to do with ML or AI. It is actually a generic number, but has some significance. In Machine Learning, it doesn't matter what the actual random number is, anything more than 0 is sufficient enough.

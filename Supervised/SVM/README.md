## Index
**Support Vector Machine (SVM)** is a powerful machine learning algorithm used for **linear** or **nonlinear classification**, **regression** and even **outlier detection** tasks. SVMs can be used for a variety of tasks, such as **text classification**, **image classification**, **spam detection**, **handwriting identification**, **face detection** and **anomaly detection**. SVMs are adaptable and efficient in a variety of applications because they can manage **high-dimensional** data and **nonlinear relationships**.

## Definition
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
#### A Support Vector Machine (SVM) is a powerful and versatile supervised Machine Learning model, capable of performing [_linear_][1] or [_nonlinear classification_][1], _regression_, and even _outlier detection_. 

> * SVMs are sensitive to the _feature scales_.
> * SVMs are particularly well suited for classification of complex _small_- or _medium-sized_ datasets.
> * SVM is a [non-probabilistic][] binary linear classifier. [_Wiki_][2]
> * Although methods such as _`Platt scaling`_ exist to use SVM in a probabilistic classification setting.[_Wiki_][2]
* Unlike Logistic Regression classifiers, SVM classifiers do not output probabilities for each class.
* It is one of the most popular models in Machine Learning, prior to Neural Network for pictures and videos SVM was used intensively.
### Linear SVM Classification
![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* The following picture is a demonstration why we need a Linear SVM Classifier.
* At the left side we can see some scenarios where linear classification wrongly done.
* The other side is the correct way how linear SVM works, both are on **_Iris_** dataset.
<img src="https://user-images.githubusercontent.com/12748752/158370041-e271cffa-7cf4-49b8-b71e-0cd53a0b3aec.png" width=50% />

#### <ins>_Large Margin Classification_</ins>

* The two classes can clearly be separated easily with a straight line (they are _linearly separable_). 
#### Left side:
* The left plot shows the **_decision boundaries_** of three possible linear classifiers. 
* The model whose decision boundary is represented by the Green dashed line is so bad that it does not even separate the classes properly.
* The other two models work perfectly on this training set, but their decision boundaries come so close to the instances that these models will probably not perform as well on new instances.
#### Right side:
* In contrast, the solid line in the plot on the right represents the **_decision boundary_** of an SVM classifier; this line not only separates the two classes but also stays as far away from the closest training instances as possible. 
* You can think of an SVM classifier as fitting the _widest possible street_ (represented by the parallel dashed lines) between the classes. 
* This is called **_large margin classification_** or **_maximum-margin hyperplane_**
* Notice that adding more training instances “_off the street_” will not affect the decision boundary at all: it is fully determined (or “supported”) by the instances located on the edge of the street. 
* These instances are called the **_support vectors_** (they are circled in the above picture) or Samples on the margin are called the support vectors.

### _Hard Margin Classification_
* If the training data is linearly separable, we can select two parallel hyperplanes that separate the two classes of data, so that the distance between them is as large as possible. 
* The region bounded by these two hyperplanes is called the "margin"(doted lines) and the maximum-margin hyperplane is the hyperplane that lies halfway between them. 
* With a normalized or standardized dataset, these hyperplanes can be described by the equations

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/72/SVM_margin.png/450px-SVM_margin.png" align="left" width=25% />

#### Any hyperplane can be written as the set of points **x** satisfying - <b>w<sup>T</sup>x - b= 0</b>
#### With a normalized or standardized dataset, these hyperplanes can be described by the equations-
#### Anything on or above this boundary is of one class, with label 1 - <b>w<sup>T</sup>x - b= 1</b>
#### Anything on or below this boundary is of the other class, with label −1 <b>w<sup>T</sup>x - b= -1</b>
#### Geometrically, the distance between these two hyperplanes is <img src="https://latex.codecogs.com/svg.image?\frac{\mathbf{2}}{||\mathbf{w}||}" align="center" /> so to maximize the distance between the planes we want to minimize <img src="https://latex.codecogs.com/svg.image?{\displaystyle&space;\|\mathbf&space;{w}&space;\|}" align="center" />. The distance is computed using the distance from a point to a plane equation. We also have to prevent data points from falling into the margin, we add the following constraint: for each {\displaystyle i}i either 

* When we strictly impose that all instances must be _off the street_ and on the right side, this is called hard margin classification.
#### There are two main issues with hard margin classification. 
  * First, it only works if the data is linearly separable. 
  * Second, it is sensitive to outliers.

### _Soft Margin Classification_
* The objective of the soft margin classification is to find a good balance between keeping the street as large as possible and limiting the margin violations (i.e., instances that end up in the middle of the street or even on the wrong side).
* To extend SVM to cases in which the data are not linearly separable, the **_hinge loss_**(parameter **_C_**) function is helpful

> #### _If your SVM model is overfitting, you can try regularizing it by reducing C._
### _Hyperparameters_
<img src="https://user-images.githubusercontent.com/12748752/159112742-b72efa06-3183-4214-8653-fcfdbb148e8e.png" width=50%/>

* When creating an SVM model using Scikit-Learn, we can specify a number of hyperparameters. C is one of those hyperparameters. 
* If we set it to a low value, then we end up with the model on the left.
* With a high value, we get the model on the right.
* **Margin violations are bad.**
   *  It’s usually better to have few of them.
   *   However, in this case the model on the left has a lot of margin violations but will probably generalize better


[1]: https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/README.md#linear-classification-vs-non-linear-classification
[2]: https://en.wikipedia.org/wiki/Support-vector_machine#:~:text=Given%20a%20set%20of%20training,use%20SVM%20in%20a%20probabilistic
### Nonlinear SVM Classification
![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
## SVM Regression
![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

## References
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [SVM Link](http://www.statsoft.com/Textbook/Support-Vector-Machines#index)
* [Wiki](https://en.wikipedia.org/wiki/Support-vector_machine#Hard-margin)
* [Hands-On..](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/)

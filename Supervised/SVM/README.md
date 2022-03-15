## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

## Definition
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
#### A Support Vector Machine (SVM) is a powerful and versatile supervised Machine Learning model, capable of performing [_linear_][1] or [_nonlinear classification_][1], _regression_, and even _outlier detection_. 

> * SVMs are sensitive to the feature scales.
> * SVMs are particularly well suited for classification of complex _small_- or _medium-sized_ datasets.
> * SVM is a [non-probabilistic][] binary linear classifier. [_Wiki_][2]
> * Although methods such as _`Platt scaling`_ exist to use SVM in a probabilistic classification setting.[_Wiki_][2]

### Linear SVM Classification
* The following picture is a demonstration why we need a Linear SVM Classifier.
* At the left side we can see some scenarios where linear classification wrongly done.
* The other side is the correct way how linear SVM works, both are on **_Iris_** dataset.
<img src="https://user-images.githubusercontent.com/12748752/158370041-e271cffa-7cf4-49b8-b71e-0cd53a0b3aec.png" width=50% />
#### Left side:
* The two classes can clearly be separated easily with a straight line (they are linearly separable). 
* The left plot shows the decision boundaries of three possible linear classifiers. 
* The model whose decision boundary is represented by the < a style="color:red;">Blue dashed</a> line is so bad that it does not even separate the classes properly.
* The other two models work perfectly on this training set, but their decision boundaries come so close to the instances that these models will probably not perform as well on new instances.




* Given a dataset, the algorithm tries to divide the data using **_hyperplanes_** and then makes the predictions.  
* While other classifiers, when classifying, predict the probability of a data point to belong to one group or the another, SVM directly says to which group the datapoint belongs to without using any probability calculation.


* It is one of the most popular models in Machine Learning, prior to Neural Network for pictures and videos SVM was used intensively.



[1]: https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/README.md#linear-classification-vs-non-linear-classification
[2]: https://en.wikipedia.org/wiki/Support-vector_machine#:~:text=Given%20a%20set%20of%20training,use%20SVM%20in%20a%20probabilistic

### Linear SVM Classification
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)


## References
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [SVM Link](http://www.statsoft.com/Textbook/Support-Vector-Machines#index)

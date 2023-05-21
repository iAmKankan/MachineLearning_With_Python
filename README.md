## Index 
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
### [_Mathematical Perspective on AI-ML_](https://github.com/iAmKankan/Neural-Network/blob/main/ai-ml-math.md)
#### [Bias Varience](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/bias-varience.md)
### _Machine Learning_
* [_What is Machine Learning_](#what-is-machine-learning)
* [_Machine Learning Life Cycle_](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/MachineLearning_LifeCycle/README.md)
  * _Training-Validation-Error_
    * [Error Train-Test Validation](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/training_performance-evaluation#readme)
  * _Model Training_
    * [Gradient Descent](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/training/gradient_descent.md)
       * [Batch Gradient Descent](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/training/batch_gd.md)
       * [Stochastic Gradient Descent](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/training/stochastic_gradient_descent.md)
### [_Supervised Learning_](https://github.com/iAmKankan/MachineLearning_With_Python/tree/master/Supervised) 
### [_Unsupervised Learning_](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/unsupervised/README.md)

### [_Terminologies_](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/terminologies.md)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
   
## What is Machine Learning
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* Machine Learning is the science (and art) of programming computers so they can _learn from data_.
* Here is a slightly more general definition:
> #### Machine Learning is the field of study that gives computers the ability to learn without being explicitly programmed.
> _— Arthur Samuel, 1959_
* And a more engineering-oriented one: 
> #### A computer program is said to learn from experience E with respect to some task T and some performance measure P, if its performance on T, as measured by P, improves with experience E. 
> — _Tom Mitchell, 1997_

### Software Engineering Vs AI/ML
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<p align="center">
 <img src="https://user-images.githubusercontent.com/12748752/186307281-6c54df9f-2544-4610-a16a-cac2b78b866b.png" width=70%/>
 <br><ins><i><b>Here the `rules` is difined as `models`</b></i></ins>
</p>

### Machine Learning Application Flow
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<p align="center">
   <img src="https://user-images.githubusercontent.com/12748752/207588605-0800a3e5-7655-4683-9d90-fb15405b8d78.png" width=60%/>
</p>

### Learning Paradigm
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
 
<p align="center">
  <img src="https://user-images.githubusercontent.com/12748752/186326497-c540fae4-3267-4e4e-ac6e-469037fd4e9a.png" width=70%/>
</p>

To learn the parameters, we follow this paradigm 
* Collect lots of data pairs (Input Vector, Output Vector) = $\large{\color{Purple} (x, y)}$
* Guess for the form of the hypothesis function $\large{\color{Purple} h(x; w)}$
  * Example : $\large{\color{Purple}h(x; w)= w_0+w_1x_1 + w_2x_2}$ 
* For an arbitrary guess for $\large{\color{Purple}w}$
  * We will get some $\large{\color{Purple} \hat{y}= h(x; w)}$  $\textrm{which will not match the ground truth } \large {\color{Purple} y}$
* Define a cost function $\large{\color{Purple} J(y, \hat{y}(w))}$ depending on the difference.
* Find optimal $\large{\color{Purple} w}$ by minimizing $\large{\color{Purple} J(w)}$.
* By using some optimization procedure such as Gradient Descent.

### Machine Learning Algorithms Based on Trainging
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Machine Learning systems can be classified according to the amount and type of supervision they get during training. 
* There are four major categories:

<img src="https://user-images.githubusercontent.com/12748752/150331825-26bc70db-8c11-4d0a-bf54-445d32cc03a8.png" width=100% />

### Based on the Performence(_Handling Outliers_)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<img src="https://user-images.githubusercontent.com/12748752/146688585-e2ecc295-c3e0-4ea8-acb1-ad03a8ec8ce6.png" width=110% />

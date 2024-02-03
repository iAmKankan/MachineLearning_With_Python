## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Voting, Bagging-Pasting, Out of the Box Evalution](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Ensemble-Learning_and_Randon-Forest/Voting_Bagging_Pasting_OoBEvalution.md)
* [Ensemble Learning and Random Forests](https://github.com/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Ensemble-Learning_and_Randon-Forest/RandomForest.md)

### ⬛ $\Large {\color{blue}\underline{\mathcal{Ensemble\ Learning\ and\ Random\ Forests:}}}$
### 🔲 $\large {\color{Purple}\underline{\textrm{Wisdom of the Crowd:}}}$
Suppose you pose a complex question to thousands of **random people**, then **aggregate** their answers. In many cases you will find that this **aggregated answer** is better than an expert’s answer. This is called the **wisdom of the crowd**. 

Similarly, if you **aggregate** the predictions of **a group of predictors** (such as **classifiers** or **regressors**), you will often get better **predictions** than with the best **individual predictor**. 
* Here **A group of predictors** is called an **_Ensemble_**,
* Thus, this technique is called _**Ensemble Learning**_, and
* **An Ensemble Learning algorithm** is called an **_Ensemble method_**.
  
### 🔲 $\large {\color{Purple}\underline{\textrm{Ensemble Learning:}}}$

**Ensemble methods** combine the predictions of <ins>several base estimators</ins> **built with a given learning algorithm** in order to improve <ins>generalizability</ins> / <ins>robustness</ins> over a **single estimator**.

**Ensemble methods** work **best** when the <ins>predictors are as independent as possible from one another</ins>. **One way to get diverse classifiers** is to train them using very <ins>different algorithms.</ins>. This increases the chance that they will make very different types of **errors**, <ins>improving the ensemble’s accuracy</ins>.

Two very famous examples of ensemble methods are **gradient-boosted trees** and **random forests**.

More generally, ensemble models can be applied to **any base learner** beyond trees, in **averaging methods** such as **Bagging methods**, **model stacking** or **Voting** or in **boosting** as **AdaBoost**.

* $\large {\color{Purple}\underline{\textrm{Base learners}}}$ are the first level of an ensemble learning architecture and each one of them is **trained to make individual predictions**. 
* $\large {\color{Purple}\underline{\textrm{Meta learners}}}$ on the other hand are in the second level and they are **trained on the output of the base learners**. 

### Types of Ensemble Methods
There are various types of ensemble learning methods, including:

1. **Bagging (Bootstrap Aggregating):** This method involves training multiple models on random subsets of the training data. The predictions from the individual models are then combined, typically by averaging.
2. **Committe Machine:**
3. **Stacking:** This method involves using the predictions from one set of models as input features for another model. The final prediction is made by the second-level model.
4. **Boosting:** This method involves training a sequence of models, where each subsequent model focuses on the errors made by the previous model. The predictions are combined using a weighted voting scheme.


### ♠️  $\large {\color{purple}1.\underline{\textrm{Bagging}}}$
Bootstrap Aggregating, also known as bagging, is a machine learning ensemble meta-algorithm designed to improve the stability and accuracy of machine learning algorithms used in statistical classification and regression. It decreases the variance and helps to avoid overfitting. It is usually applied to decision tree methods. Bagging is a special case of the model averaging approach. 


### ♠️ $\large{\color{purple}4.\underline{\textrm{Boosting:}}}$
Boosting is a method used in machine learning to <ins><b>reduce errors</b></ins> in <ins>predictive data analysis</ins>. 

Boosting is an **ensemble** modeling technique that attempts to build a strong classifier from the **number of weak classifiers**. It is done by building a model by using weak models in series. 

### $\large{\color{purple}\underline{\textrm{ADA Boost}}}$

1. **Firstly**, a model is built from the training data.
2. Then the **second model** is built which tries to **correct the errors** present in the **first model**.
3. This procedure is continued and <ins>models are added</ins> until either <ins><b>the complete training data set is predicted correctly</b></ins> or <ins><b>the maximum number of models are added</b></ins>. 

### $\large{\color{purple}\underline{\textrm{Mathametical Expression}}}$

$$\Large{\color{Purple}C_{(m-1)}(x)= \alpha_{1}k_{1}(x)+\alpha_{2}k_{2}(x)+\cdots+\alpha_{m-1}k_{m-1}(x) }$$

* I am going to denote by $\large{\color{purple}C}$ of $\large{\color{purple}x}$ of $\large{\color{purple}(m-1)^{th}}$ stage classifier,
* That is obtained by basically adding the outputs of all this individual classifies. E.g $\large{\color{purple}k_1, k_2 ,\cdots, k_{m-1}}$
* $\large{\color{purple}\alpha_1, \alpha_2 ,\cdots, \alpha_{m-1}}$ these are the weights.
* $\large{\color{purple}k_1}$ is a classifier that I added in the <ins><b>first stage</b></ins>.
* $\large{\color{purple}k_2}$ is the classifier added in the <ins><b>second stage</b></ins> and so on so forth .
* $\large{\color{purple}k_{m-1}}$ is a classifier added in the <ins><b>(m-1) stage</b></ins> okay.

### $\large{\color{purple}\underline{\textrm{Error or Loss}}}$

Now, I am going to take this above equation and look at the **residual error**, as I can consider this as a **prediction problem**. Look at the **residual error** of the predictor and then <ins><b>train the below classifier</b></ins> $\large{\color{purple}k_{m}}$ to **minimize** the **residual error**.

$$\Large{\color{Purple}C_{(m)}(x)= C_{(m-1)}(x) + \alpha_{m}k_{m}(x)}$$


#### So what will be $\large{\color{purple}\alpha_m}$ here? 
$\Large Answer:$ Its just selecting classifiers.

* So I can just take the **residual error** of $\large{\color{purple}c_{m-1}}$ and then use that to train $\large{\color{purple} k_{m}(x)}$ and then add it here.
* In fact $\large{\color{purple}\alpha_{m} }$ can be **1**. it can be one does not matter because the $\large{\color{purple}k_m(x)}$ will actually align itself in the direction of the residual so I can just add it here so it is fine.
* And it is actually a good way to do it if you are doing **regression**. I can take this as they can take the **residual error** and then train my $\large{\color{purple}k_m}$ to actually go in the **direction of the residual**.


⚛️ I can actually do this and get a **boosting** like algorithm for <ins><b>Regression</b></ins> just <ins><b>by training it along the direction of a residual</b></ins>.

⚛️ But when I am doing <ins><b>Classification</ins></b> that is not necessarily the right thing to do. So, people come up with **different kinds of loss functions** and then they try to improve the error in **classification**, so the **loss function** we look at is the **exponential loss**.


### <ins>Exponential Loss</ins>:

$$\Huge{\color{Purple}e^{-y_{i}f(x_i)}}$$

### <ins>Exponential Loss on our equation</ins>:

$$\Large{\color{Purple}\boxed{E = \sum_{i=1}^{N} e^{-y_{i}(C_{(m-1)}(x) + \alpha_{m}k_{m}(x))}}}$$

$$\Large{\color{purple}\normalsize{\textrm{ We got the above by expanding- }} \large \sum_{i=1}^{N} e^{-y_{i}f(x_i)}}$$

<p align="center">
  <ins><b><i> Exponential Loss on m<sup>th</sup> Classifier</i></b></ins> 
</p>

This was not the way **ADA BOOST** was originally derived, **ADA BOOST** was derived in a completely different way and later on about five years after they publish **ADA BOOST** they kind of discovered the connection between this kind of <ins><b>forward stage ways modeling</b></ins> or <ins><b>additive modeling</b></ins> and <ins><b>exponential loss</b></ins> they said okay, I can do forward stage wise modeling with and **exponential loss** function I end up with **ADA BOOST** that connection was discovered five years later. But now almost always people except in the theory community, in the machine learning community is always introduced like this.

#### Lets  re-write

$$\Large{\color{Purple}\begin{matrix*}[l]
E &=& \sum\limits_{i=1}^{N} e^{-y_{i}(C_{(m-1)}(x) + \alpha_{m}k_{m}(x))} \\
&=& \sum\limits_{i=1}^{N} e^{-y_{i} \alpha_m k_m (x_i)}  \normalsize{;} \Large \Big\[ \normalsize{ \textrm{ Where }  w_i^{(m)} = e^{-y_i C_{m-1}(x_i)}} \Large \Big \] \\
\end{matrix*}}$$

* The weight $\large{\color{purple}w}$ of the $\large{\color{purple}i^{th}}$ data point, at the $\large{\color{purple}m^{th}}$ stage is essentially e power minus y sub i C sub m minus one of x sub i or $\large{\color{purple}e^{-y_i C_{m-1}(x_i)}}$ .
* So what is this  $\large{\color{purple}e^{-y_i C_{m-1}(x_i)}}$ ? It is a loss I have incurred on that point $\large{\color{purple}x_i}$ up till the $\large{\color{purple}m-1}$ stage.

#### I am going to break that sum up into two components


$$\Large{\color{Purple}E = \underbrace{\sum w_i^{(m)} e^{-\alpha_m}}_{y_i=k_m(x_i)} + \underbrace{\sum w_i^{(m)} e^{\alpha_m}}\_{y_i \neq k_m(x_i)} }$$

* $\large{\color{purple} \sum w_i^{(m)} e^{-\alpha_m}}$ ; all the correctly Classified datapoints.
* $\large{\color{purple} \sum w_i^{(m)} e^{\alpha_m}}$ ; all the wrongly Classified datapoints.
 
#### What is the best classifier that I can find at the m<sup>th</sup> stage?
$\Large Answer:$ Well, the best classifier can find the one for which this side ($\large{\color{purple} \sum w_i^{(m)} e^{\alpha_m}}$ ) is empty, Which means everything has been classified correctly, so that is the best classifier.

* But, remember our classifiers are **all weak classifiers** and exactly that was the <b><ins>basic assumption</b></ins> we were starting with.
* The classifiers are all weak classifiers I can do only **slightly better than random**, so I have to get nearly **half the data points incorrect**.

<b><ins>So which half should go here at the left which half should come here at the right?</b></ins> and then we can move one data point from to here that here to make it better than half, 
* So which half should go here which half should come here?
* Which will incur less penalty?

$\Large Answer:$ All $\large{\color{purple}w^m }$  , so all the $\large{\color{purple}w}$ s that have a <b><ins>large value</b></ins> should come at the **left hand side** because they get multiplied by $\large{\color{purple}e^{-\alpha}}$ ( so they will besome small). 

So what are **w**’s is a small values- the ones that I have correctly classified up till the previous point. **w** is the large value - that are the ones that I have incorrectly classified up to the previous point.

At the <b>m<sup>th</sup></b> stage what I should be looking at is <b><ins>to get the data points which I misclassified from the previous stage, try to get them correctly as many as possible</b></ins>. 


So that is essentially the intuition behind ADABOOST, so at every stage what you do is you try to look at the previous stage see which are the data points you misclassified it tries to get them correctly in this stage, right. It is okay if you make mistakes on data points that you have correctly classified till the previous stage why is it okay?. Because those classifiers can adjust for it, then we will look at how we will do this again.


$$\Large{\color{Purple}\sum\limits_{y_i= k_m(x_i)} w_i^{(m)} = W_c \ \ ; \ \  \sum\limits_{y_i \neq k_m(x_i)} w_i^{(m)} = W_e }$$


So, I am going to call, so it is all the weights of all the data points I got correct at <b>m<sup>th</sup></b> stage, likewise weight of all the data points I made a mistake on at the <b>m<sup>th</sup></b> stage

Then I can write my $\large{\color{purple}e}$’s simply as the following-

$$\Large{\color{Purple}E = W_c e^{-\alpha_m} + W_e e^{\alpha_m}}$$

* The value of $\large{\color{purple}\alpha}$ really does not matter in my choice of $\large{\color{purple}k_m}$ , 
* Regardless of value of $\large{\color{purple}\alpha_m}$ whatever argument I gave you this no holes, the idea is to see how much of the **weight** you can push to  $\large{\color{purple}W_c}$ and how less of the weight you keep in  $\large{\color{purple}W_e}$ means total of weight or total of  $\large{\color{purple}W}$
*  $\large{\color{purple} W}$ is a **constant**.  $\large{\color{purple}W_c + W_e }$ are **constants**
*  The goal is now to see how much weight you can push into  $\large{\color{purple}W_c}$ as **posted**,
*   $\large{\color{purple}k_m}$ will be the classifier that rise as to my  $\large{\color{purple}W_c}$, so how we do this well you can use you can classifier they images that can assign based data point, we discussed very briefly in session the case, we can assign ways to data points and you can essentially multiply the error that you make on a data point by the corresponding weight.

* So the error that you make you multiplied by the corresponding weight so that you can use weighted minimize other ways of doing this, so one way people see what I am saying over km , you see what you are supposed to do to get your k, the km is such that maximum weight goes into Wc they are splitting your W into two parts and depending on what data points are making mistakes on right, the data points you do not make mistakes on contributed Wc the data points you make mistakes on contribute of e. If you want to see how much larger you can Wc. We basic that is the classifier you have to find, before that you use some kind of a payment method, so one way of achieving this is do the following you are saying weights to all the data points now what you do, if you go and sample some of these data points according to their weights, create a new training set by sampling from 582 this data points are given things according to the weights, so what does this mean points for which the weight is higher you get to sample more often into this data sets, points for which the weights are very low I do not even appear in the data set, right. So the points appears multiple times in the data set then when you are trying to minimize the training error you are likely to get a point correct, so instead of using a directly using a weighted training algorithm people simulate that by sampling from the data weights okay, so what has happened unfortunately because of this I change of tends to compact by bagging and boosting in the minds of people and if you look at some of the data mining text books especially some of the earlier data mining textbooks exciting and boosting we needed will described in a very similar fashion right, what do you do in bagging whenever you add a new classified.

### $\large {\color{Purple}\underline{\textrm{Bagging Vs Boosting}}}$

So in the older textbooks how they describe is that what you do in 
* **Bagging** <ins><b>is every time you generate a new sample you generate it uniformly, with a replacement</ins></b>.
* **Boosting** the differences is - <ins><b>every time we generate a new sample you use the prediction error from the previous stage</ins></b>
* There is the only difference between **bagging** and **boosting**. But operationally if you think about it, **boosting** is <ins><b>inherently serial</ins></b> and then <ins><b>there is this error minimization property </ins></b>.

But people just tend to think of boosting as bagging with the different sampling distribution, which is incorrect. At the fundamental principles of the two things are very different.

> #### So we have found $\large {\color{Purple}k_m}$ , so we all know how to find $\large {\color{Purple}k_m}$ you do some kind of **weighted error minimization** and you find $\large {\color{Purple}k_m}$.

### $\large {\color{Purple}\underline{\textrm{Finding -}\Large \alpha_m}}$

Regardless of what value of $\large {\color{Purple}\alpha_m}$ you choose the minimizer for $\large {\color{Purple}k_m}$ is the one that gives you maximum weight into $\large {\color{Purple}W_c}$. But then having chosen a $\large {\color{Purple}k_m}$ I know have to choose an $\large {\color{Purple}\alpha_m}$ that gives me the error detection, so how do you go about doing that.

$$\Large{\color{Purple}\begin{matrix*}[l]
\dfrac{\partial E}{\partial \alpha_m} &=& - W_c e^{-\alpha_m} + W_e e^{\alpha_m} = 0 \\
-W_c + W_e^{2 \alpha_m}  &=& 0 \\
\alpha_m &=& \dfrac{1}{2} \ln \left \( \dfrac{W_c}{W_e} \right \)\\
 &=& \dfrac{1}{2} \ln \left \( \dfrac{W - W_e}{W_e} \right \)\\
 &=& \dfrac{1}{2} \ln \left \( \dfrac{1 - err_m}{err_m} \right \)\\
 err_m &=& \dfrac{W_e}{W} \\
\end{matrix*}}$$





![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)


### Description of the Technique

Suppose a set D of d tuples, at each iteration i, a training set Di of d tuples is selected via row sampling with a replacement method (i.e., there can be repetitive elements from different d tuples) from D (i.e., bootstrap). Then a classifier model Mi is learned for each training set D < i. Each classifier Mi returns its class prediction. The bagged classifier M* counts the votes and assigns the class with the most votes to X (unknown sample).


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

### References:
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

* Hands-On Machine Learning with Scikit-Learn Keras and TensorFlow Concepts Tools and Techniques to Build Intelligent Systems by Aurélien Géron, 2nd Edition
* [Scikit Learn](https://scikit-learn.org/stable/modules/ensemble.html#voting-classifier)
* IITM - Bala

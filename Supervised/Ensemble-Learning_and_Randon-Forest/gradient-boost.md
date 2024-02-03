### 🔲 $\Large{\color{Purple}\underline{\textrm{Gradient Boosting}}}$
The characteristic of boosting, so at every stage, you have to look at the errors from the previous stage and you are trying to reduce that right. So we looked at AdaBoost right, one of the most popular boosting algorithms. 

I then told you that AdaBoost uses exponential loss and that it is related to the logistic loss. So you can use the logistic loss function and derive a boosting algorithm called **logit boost** right. 

But it is very similar properties to AdaBoost. However, AdaBoost is more popular, especially from an analysis point of view and things like this because it is not nice properties, okay. 

There is yet another approach to boosting that is gaining a lot of currency recently. It is called a **gradient boosting**.

$$\Large{\color{Purple}T(x; \theta)= \sum_{j=1}^{J} \gamma_j I (x \in R_j)}$$

* This is the Regression Tree.
* $\large{\color{purple}I}$ is an **identity function**, which is $\large{\color{purple}1}$ if $\large{\color{purple}x}$ belongs to $\large{\color{purple}R_j}$ otherwise $\large{\color{purple}0}$ .
* This is summing over all regions, $\large{\color{purple}R_1,R_2, \cdots,R_j}$
* Gamma sub j $\large{\color{purple}\gamma_j}$ is essentially the output I am going if to produce if $\large{\color{purple}x}$ lies in $\large{\color{purple}R_j}$.
* What is the theta here: It is all the specification of the $\large{\color{purple}R_j}$ 's and the $\large{\color{purple}\gamma_j}$ 's for each of those regions, $\large{\color{purple}\theta = \\{ R_j, \gamma_j\\}_{j=1}^J}$.
* Typically, we pick some **loss function** if it is **regression** it is going to be **squared loss**

### Loss

$$\Large{\color{Purple}\hat{\theta} = avgmin__{\theta}= \sum_{j=1}^{J} \sum_{x_i \in R_i} L(y_i,\gamma_j)}$$


I look at the loss incurred when 
* the actual output is $\large{\color{purple}y_i}$.
* The output I am giving you is $\large{\color{purple}\gamma_j}$ ,
* so for all data points $\large{\color{purple}x}$ that belongs to a region $\large{\color{purple}R_j}$ the output will be $\large{\color{purple}\gamma_j}$, so this is essentially the loss there.
*  $\large{\color{purple}\sum_{j=1}^{J}}} this is the sum over all regions. This is just recapping the decision trees for you right.
*  And then we looked at greedy methods for finding $\large{\color{purple}R_j}$ right, and given an $\large{\color{purple}R_j}$; we knew how to fit $\large{\color{purple}\gamma_j}$ right, so given that we looked at some greedy search methods right.

### Boosted Tree
So you can do, you can do boosting with trees also just like you did boost with other classifiers you can do boosting with trees right.

$$\Large{\color{Purple}f_M(x) = \sum_{m=1}^{M} T (x;\theta_m)}$$

So I have $\large{\color{purple}M}$ trees so essentially it is taken some of the output of all the $\large{\color{purple}M}$ trees that gives me my **boosted tree**.
* This is not a single tree okay it is now a **forest**,  a collection of trees is a forest. Next-

$$\Large{\color{Purple}\hat{\theta}\_m = avgmin_{\theta}= \sum_{n=1}^{N} L(y_i, f_{m-1}(x_i)+ T (x_i, \theta_n)}$$


So this is essentially when I find the parameters for the $\large{\color{purple}m^{th}}$ tree.
* I am going to look at the **classifier** or the **predictor** that is formed by the first $\large{\color{purple}M-1}$ **trees** right.
* And then I am going to find that tree okay, whose output I will add to this **predictor** and you search for computing the loss.

 

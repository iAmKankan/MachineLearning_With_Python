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

$$\Large{\color{Purple}\hat{\theta} = avgmin_{\theta}= \sum_{j=1}^{J} \sum_{x_i \in R_i} L(y_i,\gamma_j)}$$


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

$$\Large{\color{Purple}\hat{\theta}\_m = avgmin_{\theta}= \sum_{i=1}^{N} L \big \( y_i, f_{m-1}(x_i)+ T (x_i, \theta_m) \big \) }$$


So this is essentially when I find the parameters for the $\large{\color{purple}m^{th}}$ tree.
* I am going to look at the **classifier** or the **predictor** that is formed by the first $\large{\color{purple}m-1}$ **trees** right.
* And then I am going to find that ($\large{\color{purple} T (x_i, \theta_m}$ ) tree, whose output I will add to this **predictor** (($\large{\color{purple}f_{m-1}(x_i)}$ )and you search for computing the loss.

So for every data point in my training data  I look at the way $\large{\color{purple} y}$, I look at the output produced by the $\large{\color{purple} m-1}$ stage tree, I look at the value that is added by the $\large{\color{purple} m^{th}}$ tree, so this is the output produced by the $\large{\color{purple} m^{th}}$ tree I look at the value added by the $\large{\color{purple} m^{th}}$ tree to that right. And then I will compute the loss function.

 So when will it be the **residual error**, when it is a regression task, and **squared error is my metric**. So and the loss function is squared error right, and I am so trying to solve the regression problem right, then essentially what I will have to do here is take the residual error. 
 
* First build one tree to predict your output as best as possible,
* The predictor function as best as possible will build a tree, then you will take the residual of that,
* build another tree that predicts the residual as well as possible and add the output to this.
* And then take the combined thing find the residual of that build the third tree which will predict the residual and add it back to this and so on so forth, you just keep doing this.

So, with regular decision tree learning given the  $\large{\color{purple}R_j}$'s , finding the  $\large{\color{purple}\gamma_j}$’s is easy. But the problem is finding the $\large{\color{purple}R_j}$'s . 
* In general, it becomes a little tricky finding the region's because I have to take into account the other tree's output also.
* But if I am talking about the squared error. It is very easy because things nicely decouple when I am talking about a squared error. I do not have to worry about  $\large{\color{purple}F_{M-1}}$ after I compute the residual.
* The residual could have been generated by any **classifier** any **regress**; I do not even have to worry about the fact what generated the residual was a tree, all I need is just the residual.
* The residual then becomes any function right, so with **squared error** boosting becomes just like learning a series of decision trees, nothing special about it.
* But if you have other kinds of **loss functions**, then we will have to worry about how to accommodate it, but at least in this case.

### Squared error loss:
Pick the tree that best predict the residual.
* $\large{\color{purple}y_i -f_{m-1}(x_i)}$ - The target function.
* $\large{\color{purple}\hat{\gamma} _{jm}}$- just the average residual error in the j<sup>th</sup> region or $\large{\color{purple}R\_{jm}}$


### For 2 class problems and exponential loss functions
It becomes the same as doing **ADA BOOST** with trees.

  
### Differentiable Loss Function
**Differentiable loss function** some loss function which is which I can take the derivative of.

* If you want to take a numerical approach to optimize this kind of a loss function typically what will I end up doing I will start with some guess for a solution,
* take the gradient of the loss function with respect to the parameters at that solution point (essentially a gradient descent).
* Then I will compute the gradient, and then I will move in the opposite direction of the gradient
* and I will move a small step in the opposite direction of the gradient go to a new place and compute the gradient again and then move again and so on so forth until I converge to the right answer.

So, It means- at every point, I give you a parameter vector, but the parameter vector itself is composed of a sequence of additions. So I can think of it as first starting with initial guess for my parameters, then adding something more to it, then adding something more to it, then adding something more to it, and adding something more to it, till I come to the final answer.

#### Let us try and write this down a little formally
  
$$\Large{\color{Purple}L(f) = \sum_{i=1}^{N} L(y_i, f(x_i)) }$$

$$\Large{\color{Purple}\hat{f} =avgmin_f L(f) }$$

Here $\large{\color{purple}f}$ is a $\large{\color{purple}N}$ diamentianal vector $\large{\color{purple}f= \big \( f(x_1),\cdots,f(x_N) \big \)}$ , So you can think of it as a point in n-dimensional space.


$$\Large{\color{Purple} f_0 = h_0 }$$

$$\Large{\color{Purple}f_M = \sum_{m=0}^{M}h_M  \ \; \  \ h_M  \in \mathbb{R}^N}$$

Typically you start with some solution, $\large{\color{purple}f_0}$ you start with some solution let us call it $\large{\color{purple}h_0}$. So you can think of it like this I start somewhere here that is my F0 right. And then, I compute the gradient and move in the opposite direction right, so I take a small step in this direction, so I come here that gives me a new set of parameters right. So this is 1 θ, this is another set of θ, and this will give me another F.


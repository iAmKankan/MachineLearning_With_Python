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
* What is the theta here: $\large{\color{purple}\theta = \\{ R_j, \gamma_j\\}_{j=1}^J}$

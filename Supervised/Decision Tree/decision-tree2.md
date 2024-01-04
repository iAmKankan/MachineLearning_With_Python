

### 🔲 $\Large{\color{Purple}\underline{\textrm{How to choose the best attribute at each node?}}}$
While there are multiple ways to select the best attribute at each node, two methods- $\large{\color{Purple}\textrm{Information gain}}$ and $\large{\color{Purple}\textrm{Gini impurity}}$, act as <b>popular splitting <ins>criterion</ins></b> for decision tree models. They help to evaluate the quality of each test condition and how well it will be able to classify samples into a class.

### $\Large{\color{Purple}\underline{\textrm{Entropy and Information Gain:}}}$
It’s difficult to explain information gain without first discussing **Entropy**. **Entropy** is a concept that stems from **information theory**, <ins>which measures the impurity of the sample values</ins>. It is defined with by the following formula, where: 

$$\Large{\color{Purple} \mathrm{Entropy}(S) = - \sum_{c \in C} p(c)\log_2 p(c)}$$

* $\large{\color{Purple}S}$ represents the **data set** that entropy is calculated.
* $\large{\color{Purple}c}$ represents the **classes** in set $\large{\color{Purple}S}$
* $\large{\color{Purple}p(c)}$ represents the **proportion of data points** that belong to **class** $\large{\color{Purple}c}$ to the number of total data points in the set $\large{\color{Purple}S}$


$\large{\color{Purple}Entropy}$ values can fall between $\large{\color{Purple}0}$ and $\large{\color{Purple}1}$. 
* If **all samples** in data set $\large{\color{Purple}S}$ , belong to **one class**, then <ins><b>entropy will be equal zero</b></ins>.
* If **half of the samples** are classified as **one class** and the **other half** are in **another** class, <ins><b>entropy will be at its highest at 1</b></ins>.
* **In order to select the best feature to split** on and find the **optimal decision tree**, the attribute with the <ins><b>smallest amount of entropy</b></ins> should be used.

$\large{\color{Purple}Information\ gain}$ represents <ins><b>the difference in entropy before and after a split on a given attribute</b></ins>. 
* The **attribute** with the **highest information gain** will produce the **best split** as it’s doing the **best job at classifying **the training data according to its target classification.

Information gain is usually represented with the following formula, where: 

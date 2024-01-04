

### 🔲 $\Large{\color{Purple}\underline{\textrm{How to choose the best attribute at each node?}}}$
While there are multiple ways to select the best attribute at each node, two methods- $\large{\color{Purple}\textrm{Information gain}}$ and $\large{\color{Purple}\textrm{Gini impurity}}$, act as <b>popular splitting <ins>criterion</ins></b> for decision tree models. They help to evaluate the quality of each test condition and how well it will be able to classify samples into a class.

### 🔲 $\Large{\color{Purple}\underline{\textrm{Entropy and Information Gain:}}}$
It’s difficult to explain **information gain** without first discussing **Entropy**. 

♠️ $\large{\color{Purple}Entropy}$ <ins><b> measures the impurity of the sample values</b></ins>, which is a concept that stems from information theory. 

It is defined with by the following formula, where: 

$$\Large{\color{Purple} \mathrm{Entropy}(S) = - \sum_{c \in C} p(c)\log_2 p(c)}$$

* $\large{\color{Purple}S}$ represents the **data set** that entropy is calculated.
* $\large{\color{Purple}c}$ represents the **classes** in set $\large{\color{Purple}S}$
* $\large{\color{Purple}p(c)}$ represents the **proportion of data points** that belong to **class** $\large{\color{Purple}c}$ to the number of total data points in the set $\large{\color{Purple}S}$


**Entropy** values can **fall between** $\large{\color{Purple}0}$ and $\large{\color{Purple}1}$. 
* If **all samples** in data set $\large{\color{Purple}S}$ , belong to **one class**, then <ins><b>entropy will be equals to zero</b></ins>.
* If **half of the samples** are classified as **one class** and the **other half** are in **another** class, <ins><b>entropy will be at its highest at 1</b></ins>.
* **In order to select the best feature to split** on and find the **optimal decision tree**, the attribute with the <ins><b>smallest amount of entropy</b></ins> should be used.

♠️ $\large{\color{Purple}Information\ gain}$ represents <ins><b>the difference in entropy before and after a split on a given attribute</b></ins>. 
* The **attribute** with the **highest information gain** will produce the **best split** as it’s doing the **best job at classifying** the training data according to its target classification.

**Information gain** is usually represented with the following formula, where: 

$$\Large{\color{Purple} \mathrm{Information\ Gain}(S, \alpha) = \mathrm{Entropy}(S) - \sum_{v \in v(\alpha)} \dfrac{\mid S_v \mid}{\mid S \mid}\mathrm{Entropy}(S_v)}$$

* $\large{\color{Purple}\alpha}$ represents a **specific attribute** or **class label**.
* $\large{\color{Purple}Entropy(S)}$ is the **entropy** of dataset, $\large{\color{Purple}S}$
* $\large{\color{Purple}|Sv|/ |S|}$ represents the proportion of the values in $\large{\color{Purple}S_v}$ to the number of values in dataset, $\large{\color{Purple}S}$
* $\large{\color{Purple}Entropy(S_v)}$ is the entropy of dataset, $\large{\color{Purple}S_v}$

### 🔲 $\Large{\color{Purple} Example \\# 1}$
Let’s walk through an example to solidify these concepts. Imagine that we have the following arbitrary dataset:

<p align="center">
 <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/5f6c6995-6b76-413a-9cb9-9cf25b0b31a8" width=50%/>
 <br>
</p>

For this dataset, the entropy is **0.94**. This can be calculated by finding the proportion of days where “**Play Tennis**” is “**Yes**”, which is **9/14**, and the proportion of days where “**Play Tennis**” is “**No**”, which is **5/14**. Then, these values can be plugged into the entropy formula above.

$$\Large{\color{Purple}Entropy (Tennis) = -(9/14) \log_2(9/14) – (5/14) \log_2 (5/14) = 0.94}$

We can then compute the information gain for each of the attributes individually. For example, the information gain for the attribute, “Humidity” would be the following:

Gain (Tennis, Humidity) = (0.94)-(7/14)*(0.985) – (7/14)*(0.592) = 0.151

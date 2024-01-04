

### 🔲 $\Large{\color{Purple}\textrm{How to choose the best attribute at each node?}}$
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
 <ins><b><i> Lets consider that total number of samples are 14; with in that 9 times "Yes" class appear and 5 times "No" class appear</i></b></ins> 
</p>

For this dataset, the $\large{\color{Purple}Entropy}$ is **0.94**. This can be calculated by finding the proportion of days where “**Play Tennis**” is “**Yes**”, which is **9/14**, and the proportion of days where “**Play Tennis**” is “**No**”, which is **5/14**. 

Then, these values can be plugged into the entropy formula above.

$$\Large{\color{Purple}Entropy (Tennis) = -(9/14) \log_2(9/14) – (5/14) \log_2 (5/14) = 0.94}$$

We can then compute the $\large{\color{Purple}Information\ Gain}$ for each of the attributes individually. For example, the information gain for the attribute, “**Humidity**” would be the following:

$$\Large{\color{Purple} Gain (Tennis, Humidity) = (0.94)-(7/14) \times (0.985) – (7/14)\times (0.592) = 0.151}$$


### 🔲 $\Large{\color{Purple}\underline{\textrm{Gini Impurity:}}}$ 

<ins><b>Gini impurity is the probability of incorrectly classifying random data point in the dataset if it were labeled based on the class distribution of the dataset</b></ins>. 

Similar to **entropy**, if set, S, is pure—i.e. belonging to one class) then, its impurity is zero. This is denoted by the following formula: 

$$\Large{\color{Purple}\textrm{Gini Impurity} = 1 -\sum_i (p_i)^2}$$



### ⬛ $\Large{\color{Purple}\textrm{Advantages and disadvantages of Decision Trees}}$ 

While **decision trees** can be used in a variety of use cases, other algorithms typically outperform decision tree algorithms. That said, decision trees are particularly useful for **data mining** and **knowledge discovery** tasks. Let’s explore the key benefits and challenges of utilizing decision trees more below:

### $\Large{\color{Purple}\underline{\textrm{Advantages:}}}$
- $\large{\color{Purple}\textrm{Easy to interpret:}}$ The Boolean logic and visual representations of decision trees make them easier to understand and consume. The hierarchical nature of a decision tree also makes it easy to see which attributes are most important, which isn’t always clear with other algorithms, like neural networks.

- $\large{\color{Purple}\textrm{Little to no data preparation required:}}$ Decision trees have a number of characteristics, which make it more flexible than other classifiers. It can handle various data types—i.e. discrete or continuous values, and continuous values can be converted into categorical values through the use of thresholds. Additionally, it can also handle values with missing values, which can be problematic for other classifiers, like Naïve Bayes.  

- $\large{\color{Purple}\textrm{More flexible:}}$ Decision trees can be leveraged for both classification and regression tasks, making it more flexible than some other algorithms. It’s also insensitive to underlying relationships between attributes; this means that if two variables are highly correlated, the algorithm will only choose one of the features to split on. 

### $\Large{\color{Purple}\underline{\textrm{Disadvantages:}}}$
- $\large{\color{Purple}\textrm{Prone to overfitting:}}$ Complex decision trees tend to overfit and do not generalize well to new data. This scenario can be avoided through the processes of pre-pruning or post-pruning. Pre-pruning halts tree growth when there is insufficient data while post-pruning removes subtrees with inadequate data after tree construction. 

- $\large{\color{Purple}\textrm{High variance estimators:}}$ Small variations within data can produce a very different decision tree. Bagging, or the averaging of estimates, can be a method of reducing variance of decision trees. However, this approach is limited as it can lead to highly correlated predictors.  

- $\large{\color{Purple}\textrm{More costly:}}$ Given that decision trees take a greedy search approach during construction, they can be more expensive to train compared to other algorithms. 

🌧️ ⛅ :sunny: :cloud_with_rain: 💧 :cloud_with_rain: :partly_sunny: :droplet:
:hot


|  Day |  outlook | temp | humidity | windy | play |
|:--:|:--------|:----:|:--------|:-----:|:----:|
|  1 |   :sunny:  sunny  |  hot |   :droplet: high   |  True |  no  |
|  2 | :partly_sunny:  overcast  |  hot |   :droplet: high   | False |  yes |
|  3 |   :cloud_with_rain:  rainy   | mild |  :droplet:  high   | False |  yes |
|  4 |   :cloud_with_rain:  rainy   | cool |  :droplet: normal  | False |  yes |
|  5 |   :cloud_with_rain:  rainy   | cool | :droplet: normal  |  True |  no  |
|  6 | :partly_sunny:  overcast  | cool |  :droplet: normal  |  True |  yes |
|  7 |   :sunny:  sunny  | mild |  :droplet: high   |  False |  no  |
|  8 |   :sunny:  sunny  | cool |  :droplet: normal  | False |  yes |
|  9 |   :cloud_with_rain:  rainy   | mild |  :droplet: normal  | False |  yes |
| 10 |   :sunny:  sunny  | mild | :droplet: normal  |  True |  yes |
| 11 | :partly_sunny:  overcast  | mild |  :droplet: high   |  True |  yes |
| 12 | :partly_sunny:  overcast  |  hot |  :droplet: normal  | False |  yes |
| 13 |   :cloud_with_rain:  rainy   | mild |   :droplet: high   |  True |  no  |
|  14|   :sunny:  sunny  |  hot |  :droplet: high   | False |  no  |

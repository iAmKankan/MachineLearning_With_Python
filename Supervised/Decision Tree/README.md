## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Decission Tree Classification Notebook](https://nbviewer.org/github/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Decision%20Tree/Decision%20Trees1.ipynb)
* [Decission Tree Regression Notebook](https://nbviewer.org/github/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Decision%20Tree/DecissionTree2.ipynb)
  
### ⬛ $\large{\color{Blue}\underline{\textrm{Decision tree:}}}$
### 🔲 $\large{\color{Purple}\textrm{What is a Decision Tree?}}$
A decision tree is a **flowchart-like tree structure** where-
* Each **internal node** denotes the **feature**,
* **Branches** denote the **rules** and
* The **leaf nodes** denote the **result** of the algorithm.

It is a **versatile**, **supervised machine-learning algorithm** which is used for both **classification** and **regression** problems. It is one of the very powerful algorithms. And it is also used in **Random Forest** to train on different subsets of training data, which makes random forest one of the most powerful algorithms in machine learning.

### 🔲 $\large{\color{Purple}\textrm{Decision Tree Terminologies}}$
Some of the common Terminologies used in Decision Trees are as follows:

* **Root Node:** It is the topmost node in the tree,  which represents the **complete dataset**. It is the starting point of the **decision-making process**.
* **Decision/Internal Node:** A node that symbolizes a choice regarding an input feature. Branching off of internal nodes connects them to leaf nodes or other internal nodes.
* **Leaf/Terminal Node:** A node without any child nodes that indicates a class label or a numerical value.
* **Splitting:** The process of **splitting** a node into **two or more sub-nodes** using a split criterion and a selected feature.
* **Branch/Sub-Tree:** A subsection of the decision tree starts at an internal node and ends at the leaf nodes.
* **Parent Node:** The node that **divides** into **one or more child nodes**.
* **Child Node:** The nodes that emerge **when a parent node is split**.
* **Impurity:** A measurement of the target variable’s **homogeneity** in a subset of data. It refers to the degree of randomness or uncertainty in a set of examples. The **Gini index** and **entropy** are two commonly used **impurity measurements** in **decision trees** for **classifications task**. 
* **Variance:** Variance measures how much the **predicted** and the **target variables** vary in **different samples** of a dataset. It is used for **regression problems** in decision trees. **Mean squared error**, **Mean Absolute Error**, **friedman_mse**, or **Half Poisson deviance** are **used to measure the variance for the regression tasks in the decision tree**.
* **Information Gain:** **Information gain is a measure of the reduction in impurity achieved by splitting a dataset on a particular feature in a decision tree**. The splitting criterion is determined by the feature that offers the greatest information gain, It is used to determine the most informative feature to split on at each node of the tree, with the goal of creating pure subsets.
* **Pruning:** The process of removing branches from the tree that **do not provide any additional information** or **lead to overfitting**.


<p align="center">
 <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/11372f36-4a76-419e-906f-68a028614239" width=70%/>
</p>

###  🔲 $\large{\color{Purple}\textrm{Algorithm of Decision Tree}}$

* **Step-1:** Begin the tree with <ins>the root node, says S</ins>, which contains the <ins>complete dataset</ins>.
* **Step-2:** Find the best attribute in the dataset using **Attribute Selection Measure (ASM)**.
* **Step-3:** Divide the <ins>S into subsets that contains possible values for the best attributes</ins>.
* **Step-4:** Generate the <ins>decision tree node, which contains the best attribute</ins>.
* **Step-5:** Recursively <ins>make new decision trees using the subsets of the dataset</ins> created in **Step -3**. Continue this process until a stage is reached where you cannot further classify the nodes and  called the <ins>final node as a leaf node</ins>.

###  🔲 $\large{\color{Purple}\textrm{Decision making Example of Decision Tree}}$
### $\large{\color{Purple}Example \\# 1 }$
#### Suppose we have a Picture of an animal and we need to identify the animal through Decision Tree
<p align="center">
 <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/a2d42ede-b3b7-46d7-b836-2cb8f0e38678" width=70%/>
  <br>
  <ins><b><i>  Animal Picture Identification through Decision Tree</i></b></ins> 
</p>

### 🔲 $\large \underline{\textrm{Attribute Sele}\textrm{ction Measures(ASM):}}$
### $\large{\color{Purple}\textrm{Construction of Decision Tree:}}$
* A tree can be "<ins>learned</ins>" by **splitting** the **source set** into **subsets** based on <ins><b>Attribute Selection Measures</b></ins> . 
* <ins><b>Attribute selection measure (ASM)</b></ins> is a **criterion** used in **decision tree** algorithms to **evaluate** the **usefulness** of **different attributes** for **splitting** a dataset.
* The **goal** of **ASM** is to **identify** the attribute that will create the most **homogeneous subsets** of data after the split, **thereby maximizing the information gain**.
* This process is repeated on each **derived subset** in a **recursive manner** called **recursive partitioning**.
* The **recursion** is completed when the subset at a node all has the same value of the **target variable** or **when splitting no longer adds value to the predictions**.
* The construction of a decision tree classifier does not require any **domain knowledge** or parameter setting and therefore is appropriate for **exploratory knowledge discovery**.
* **Decision trees** can handle **high-dimensional data**.

### $\large{\color{Purple}\textrm{Entropy:}}$
**Entropy** is the **measure of the degree of randomness** or **uncertainty in the dataset**. In the case of **classifications** it measures the **randomness** based on the **distribution of class labels** in the dataset.

The entropy for a subset of the original dataset having $\large{\color{Purple}K}$ number of classes for the $\large{\color{Purple}i^{th}}$ node can be defined as:

$$\large{\color{Purple} H_i = -\sum_{k \epsilon K}^{n} p(i,k)\log_2p(i,k)}$$

<ins><b>Where: </b></ins>
* **S** is the dataset sample.
* **k** is the particular class from **K** classes
* **p(k)** is the proportion of the data points that belong to class **k** to the total number of data points in dataset sample **S**. $\large{\color{Purple} p(k) = \frac{1}{n}\sum{I(y=k)}}$
* Here **p(i,k)** should not be equal to **zero**.

### Important points related to Entropy:

The entropy is 0 when the dataset is completely homogeneous, meaning that each instance belongs to the same class. It is the lowest entropy indicating no uncertainty in the dataset sample.
when the dataset is equally divided between multiple classes, the entropy is at its maximum value. Therefore, entropy is highest when the distribution of class labels is even, indicating maximum uncertainty in the dataset sample.
Entropy is used to evaluate the quality of a split. The goal of entropy is to select the attribute that minimizes the entropy of the resulting subsets, by splitting the dataset into more homogeneous subsets with respect to the class labels.
The highest information gain attribute is chosen as the splitting criterion (i.e., the reduction in entropy after splitting on that attribute), and the process is repeated recursively to build the decision tree.
Gini Impurity or index:
Gini Impurity is a score that evaluates how accurate a split is among the classified groups. The Gini Impurity evaluates a score in the range between 0 and 1, where 0 is when all observations belong to one class, and 1 is a random distribution of the elements within classes. In this case, we want to have a Gini index score as low as possible. Gini Index is the evaluation metric we shall use to evaluate our Decision Tree Model.

\text{Gini Impurity} = 1- \sum{p_i^2}  

Here,

pi is the proportion of elements in the set that belongs to the ith category.
Information Gain:
Information gain measures the reduction in entropy or variance that results from splitting a dataset based on a specific property. It is used in decision tree algorithms to determine the usefulness of a feature by partitioning the dataset into more homogeneous subsets with respect to the class labels or target variable. The higher the information gain, the more valuable the feature is in predicting the target variable. 

The information gain of an attribute A, with respect to a dataset S, is calculated as follows:

\text{Information Gain(H, A)}= H - \sum{\frac{|H_V|}{|H|}H_{v}} 

where

A is the specific attribute or class label
|H| is the entropy of dataset sample S
|HV| is the number of instances in the subset S that have the value v for attribute A
Information gain measures the reduction in entropy or variance achieved by partitioning the dataset on attribute A. The attribute that maximizes information gain is chosen as the splitting criterion for building the decision tree.

Information gain is used in both classification and regression decision trees. In classification, entropy is used as a measure of impurity, while in regression, variance is used as a measure of impurity. The information gain calculation remains the same in both cases, except that entropy or variance is used instead of entropy in the formula.

How does the Decision Tree algorithm Work?
The decision tree operates by analyzing the data set to predict its classification. It commences from the tree’s root node, where the algorithm views the value of the root attribute compared to the attribute of the record in the actual data set. Based on the comparison, it proceeds to follow the branch and move to the next node. 

The algorithm repeats this action for every subsequent node by comparing its attribute values with those of the sub-nodes and continuing the process further. It repeats until it reaches the leaf node of the tree. The complete mechanism can be better explained through the algorithm given below.

Step-1: Begin the tree with the root node, says S, which contains the complete dataset.
Step-2: Find the best attribute in the dataset using Attribute Selection Measure (ASM).
Step-3: Divide the S into subsets that contains possible values for the best attributes.
Step-4: Generate the decision tree node, which contains the best attribute.
Step-5: Recursively make new decision trees using the subsets of the dataset created in step -3. Continue this process until a stage is reached where you cannot further classify the nodes and called the final node as a leaf nodeClassification and Regression Tree algorithm.
Advantages of the Decision Tree:

 It is simple to understand as it follows the same process which a human follow while making any decision in real-life.
 It can be very useful for solving decision-related problems.
 It helps to think about all the possible outcomes for a problem.
 There is less requirement of data cleaning compared to other algorithms.
Disadvantages of the Decision Tree:

 The decision tree contains lots of layers, which makes it complex.
 It may have an overfitting issue, which can be resolved using the Random Forest algorithm.
 For more class labels, the computational complexity of the decision tree may increase.
What are appropriate problems for Decision tree learning?

Although a variety of decision tree learning methods have been developed with somewhat differing capabilities and requirements, decision tree learning is generally best suited to problems with the following characteristics:

1. Instances are represented by attribute-value pairs:

In the world of decision tree learning, we commonly use attribute-value pairs to represent instances. An instance is defined by a predetermined group of attributes, such as temperature, and its corresponding value, such as hot. Ideally, we want each attribute to have a finite set of distinct values, like hot, mild, or cold. This makes it easy to construct decision trees. However, more advanced versions of the algorithm can accommodate attributes with continuous numerical values, such as representing temperature with a numerical scale.

2. The target function has discrete output values:

The marked objective has distinct outcomes. The decision tree method is ordinarily employed for categorizing Boolean examples, such as yes or no. Decision tree approaches can be readily expanded for acquiring functions with beyond dual conceivable outcome values. A more substantial expansion lets us gain knowledge about aimed objectives with numeric outputs, although the practice of decision trees in this framework is comparatively rare.

3. Disjunctive descriptions may be required:

Decision trees naturally represent disjunctive expressions.

4.The training data may contain errors:

“Techniques of decision tree learning demonstrate high resilience towards discrepancies, including inconsistencies in categorization of sample cases and discrepancies in the feature details that characterize these cases.”

5. The training data may contain missing attribute values:

In certain cases, the input information designed for training might have absent characteristics. Employing decision tree approaches can still be possible despite experiencing unknown features in some training samples. For instance, when considering the level of humidity throughout the day, this information may only be accessible for a specific set of training specimens.

Practical issues in learning decision trees include:

 Determining how deeply to grow the decision tree,
 Handling continuous attributes,
 Choosing an appropriate attribute selection measure,
 Handling training data with missing attribute values,
 Handling attributes with differing costs, and
 Improving computational efficiency.
 
To build the Decision Tree, CART (Classification and Regression Tree) algorithm is used. It works by selecting the best split at each node based on metrics like Gini impurity or information Gain. In order to create a decision tree. Here are the basic steps of the CART algorithm:

The root node of the tree is supposed to be the complete training dataset.
Determine the impurity of the data based on each feature present in the dataset. Impurity can be measured using metrics like the Gini index or entropy for classification and Mean squared error, Mean Absolute Error, friedman_mse, or Half Poisson deviance for regression.
Then selects the feature that results in the highest information gain or impurity reduction when splitting the data.
For each possible value of the selected feature, split the dataset into two subsets (left and right), one where the feature takes on that value, and another where it does not. The split should be designed to create subsets that are as pure as possible with respect to the target variable.
Based on the target variable, determine the impurity of each resulting subset.
For each subset, repeat steps 2–5 iteratively until a stopping condition is met. For example, the stopping condition could be a maximum tree depth, a minimum number of samples required to make a split or a minimum impurity threshold.
Assign the majority class label for classification tasks or the mean value for regression tasks for each terminal node (leaf node) in the tree.
Classification and Regression Tree algorithm for Classification
Let the data available at node m be Qm and it has nm samples. and tm as the threshold for node m. then, The classification and regression tree algorithm for classification can be written as :

G(Q_m, t_m) = \frac{n_m^{Left}}{n_m}H(Q_m^{Left}(t_m)) +  \frac{n_m^{Right}}{n_m}H(Q_m^{Right}(t_m)) 

Here,

H is the measure of impurities of the left and right subsets at node m. it can be entropy or Gini impurity. 
nm is the number of instances in the left and right subsets at node m.
To select the parameter, we can write as:

t_m = \argmin_{t_m} H(Q_m, t_m) 

Example:

![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)


### Classification and Regression Tree (CART) algorithm
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

> #### Scikit-Learn uses the `Classification and Regression Tree` **(CART)** algorithm, which produces only binary trees: nonleaf nodes always have two children (i.e., questions only have yes/no answers). 
> #### However, other algorithms such as **ID3** can produce Decision Trees with nodes that have more than two children.

* _Scikit-Learn_ uses the _**`Classification and Regression Tree (CART)`**_ algorithm to train Decision Trees (also called “growing” trees). 
> #### How the algorithm works -
>> * **First** splitting the training set into _`two subsets`_ using a _`single feature`_ **k** and a threshold **t<sub>k</sub>** (e.g., “petal length ≤ 2.45 cm”). 
>> * **Then** after spliting the training set in two, it `recursively` splits the subsets using the same logic, then the sub-subsets, and so on. 
>> * **Last** It stops recursing once it reaches the maximum depth (defined by the `max_depth` hyperparameter), or if it cannot find a split that will reduce impurity. 

* A few other hyperparameters control additional stopping conditions (`min_samples_split`, `min_samples_leaf`, `min_weight_fraction_leaf` and `max_leaf_nodes`).
> #### How does it choose **k** and **t<sub>k</sub>** ?
>>  It searches for the pair (**k**,**t<sub>k</sub>** ) that produces the purest subsets (weighted by their size). 


### CART cost function for classification
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<img src="https://latex.codecogs.com/svg.image?\\J(k,t_k)&space;=&space;\frac{m_{left}}{m}G_{left}\&space;&plus;&space;\frac{m_{right}}{m}G_{right}\\&space;\\&space;\\\mathrm{Where}\left\{\begin{matrix}G_{left&space;\setminus&space;&space;right}\textrm{\&space;=&space;\&space;measures&space;the&space;impurity&space;of&space;the&space;left/right&space;subset,}\\\&space;\&space;\&space;\&space;\&space;m_{left&space;\setminus&space;&space;right}\textrm{\&space;=&space;\&space;is&space;the&space;number&space;of&space;instances&space;in&space;the&space;left/right&space;subset.}\end{matrix}\right.&space;" title="\\J(k,t_k) = \frac{m_{left}}{m}G_{left}\ + \frac{m_{right}}{m}G_{right}\\ \\ \\\mathrm{Where}\left\{\begin{matrix}G_{left \setminus right}\textrm{\ = \ measures the impurity of the left/right subset,}\\\ \ \ \ \ m_{left \setminus right}\textrm{\ = \ is the number of instances in the left/right subset.}\end{matrix}\right. " /> 




> #### Note: 
> * As you can see, the CART algorithm is a greedy algorithm: it greedily searches for an optimum split at the top level, then repeats the process at each subsequent level. It does not check whether or not the split will lead to the lowest possible impurity several levels down. A greedy algorithm often produces a solution that’s reasonably good but not guaranteed to be optimal. 
> * Unfortunately, finding the optimal tree is known to be an NP-Complete problem: it requires O(exp(m)) time, making the problem intractable even for small training sets. This is why we must settle for a “reasonably good” solution.


### Computational Complexity
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)


### Decision Tree Splitting Methods
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* It’s tough to decide which variables to put at the **root** or at different levels of the tree as internal nodes when the dataset comprises N variables. 
* Choosing any node as the root at random will not solve the problem. 
* We can receive disappointing results with limited precision if we use a random technique. 
* Researchers recommended employing criteria such-

1. Gini Impurity
2. Information Gain
3. Chi-Square

### Gini impurity
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* The division is called **pure** if all elements are accurately separated into different classes (_**an ideal scenario**_). 
* The Gini impurity is used to predict the likelihood that a randomly selected example would be incorrectly classified by a specific node. 
* **It is called an “impurity” metric because it shows how the model differs from a pure division. **
* The degree of Gini impurity ranges from **_0 to 1_**, 
    * **0** indicating that all of the elements belong to a single class 
    * **1** indicates that only one class exists. 
* The Gini impurity of value 1 indicates that all of the items are randomly distributed over various classes, whereas a value of 0.5 indicates that the elements are uniformly distributed across some classes. 

> #### A node’s gini attribute measures its impurity:
> #### A node is “pure” (gini=0) if all training instances it applies to belong to the same class.

<img src="https://latex.codecogs.com/svg.image?\mathrm{G}_i&space;=&space;1-&space;\sum_{n}^{k=1}(p_{i,k})^2" title="\mathrm{G}_i = 1- \sum_{n}^{k=1}(p_{i,k})^2" width=25% />

>> * <img src="https://latex.codecogs.com/svg.image?p_{i,k}" title="p_{i,k}" /> is the ratio of class _**k**_ instances among the training instances in the _**i<sup>th</sup>**_ node. 

* Gini index is a metric to measure how often a randomly chosen element would be incorrectly identified. 
* It means an attribute with lower gini index should be preferred. 
* Sklearn supports “ Gini ” criteria for gini index and by default, it takes “ Gini ”.


### Entropy 
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* The concept of entropy originated in thermodynamics as a measure of molecular disorder: entropy approaches zero when molecules are still and well ordered. 
* In Machine Learning, entropy is frequently used as an _impurity measure_: **a set’s entropy is zero when it contains instances of only one class**.
 
<img src="https://latex.codecogs.com/svg.image?\mathrm{H}_i&space;=&space;-&space;\sum_{k=1,\&space;p_{i,k}\neq&space;0}^{n}p_{i,k}&space;\log_2&space;(p_{i,k})" title="\mathrm{H}_i = - \sum_{k=1,\ p_{i,k}\neq 0}^{n}p_{i,k} \log_2 (p_{i,k})" width=30% />

### Gini Impurity or Entrophy?
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* The truth is, most of the time it does not make a big difference: they lead to similar trees. 
* _**Gini impurity**_ is slightly _faster to compute_, so it is a good default. 
* However, when they differ, 
    * **`Gini impurity`** **tends to isolate the most frequent class in its own branch of the tree**, 
    * While **`Entropy`** **tends to produce slightly more balanced trees**.

## Questions and Answers 
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
1. What is the approximate depth of a Decision Tree trained (without restrictions) on a training set with one million instances?
   * log2(10⁶) ≈ 20 (actually a bit more since the tree will generally not be perfectly well balanced)
2. Is a node’s Gini impurity generally lower or greater than its parent’s? Is it generally lower/greater, or always lower/greater? 
   * A node’s Gini impurity is generally lower than its parent’s. 
   * This is ensured by the CART training algorithm’s cost function, which splits each node in a way that minimizes the weighted sum of its children’s Gini impurities. 
3. If a Decision Tree is overfitting the training set, is it a good idea to try decreasing `max_depth`? 
   * If a Decision Tree is overfitting the training set, it may be a good idea to decrease `max_depth`, since this will constrain the model, regularizing it.
4. If a Decision Tree is underfitting the training set, is it a good idea to try scaling the input features? 
   * Decision Trees don’t care whether or not the training data is scaled or centered; that’s one of the nice things about them. 
   * So if a Decision Tree underfits the training set, scaling the input features will just be a waste of time.
5. If it takes one hour to train a Decision Tree on a training set containing 1 million instances, roughly how much time will it take to train another Decision Tree on a training set containing 10 million instances? 
6. If your training set contains 100,000 instances, will setting presort=True speed up training? 
7. Train and fine-tune a Decision Tree for the moons dataset by following these steps:

### Resources:
* [Geeks for Geeks](https://www.geeksforgeeks.org/decision-tree/?ref=header_search)https://www.geeksforgeeks.org/decision-tree/?ref=header_search

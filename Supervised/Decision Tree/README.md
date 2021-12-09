## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

## Decision tree
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [Decission Tree Classification Notebook](https://nbviewer.org/github/iAmKankan/MachineLearning_With_Python/blob/master/Supervised/Decision%20Tree/Decision%20Trees01.ipynb)
* [Decission Tree Regression Notebook]()
### Definition
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Decision Trees are versatile Machine Learning algorithms that can perform both classification and regression tasks, and even multi-output tasks. 
* They are powerful algorithms, capable of fitting complex datasets.
* Decision Trees are also the fundamental components of Random Forests
* One of the many qualities of Decision Trees is that they require very little data preparation. 
* In fact, they don’t require feature scaling or centering at all.
> #### Scikit-Learn uses the `Classification and Regression Tree` **(CART)** algorithm, which produces only binary trees: nonleaf nodes always have two children (i.e., questions only have yes/no answers). 
> #### However, other algorithms such as **ID3** can produce Decision Trees with nodes that have more than two children.

### Gini impurity
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
> #### A node’s gini attribute measures its impurity:
> #### A node is “pure” (gini=0) if all training instances it applies to belong to the same class.

<img src="https://latex.codecogs.com/svg.image?\mathrm{G}_i&space;=&space;1-&space;\sum_{n}^{k=1}(p_{i,k})^2" title="\mathrm{G}_i = 1- \sum_{n}^{k=1}(p_{i,k})^2" width=25% />

>> * <img src="https://latex.codecogs.com/svg.image?p_{i,k}" title="p_{i,k}" /> is the ratio of class _**k**_ instances among the training instances in the _**i<sup>th</sup>**_ node. 

* Gini index is a metric to measure how often a randomly chosen element would be incorrectly identified. 
* It means an attribute with lower gini index should be preferred. 
* Sklearn supports “ Gini ” criteria for gini index and by default, it takes “ Gini ”.

### Eliments
* **Root Node:** It represents entire population or sample and this further gets divided into two or more homogeneous sets.
* **Splitting:** It is a process of dividing a node into two or more sub-nodes.
* **Decision Node:** When a sub-node splits into further sub-nodes, then it is called decision node.
* **Leaf/ Terminal Node:** Nodes do not split is called Leaf or Terminal node.
* **Pruning:** When we remove sub-nodes of a decision node, this process is called pruning. You can say opposite process of splitting.
* **Branch / Sub-Tree:** A sub section of entire tree is called branch or sub-tree.
* **Parent and Child Node:** A node, which is divided into sub-nodes is called parent node of sub-nodes where as sub-nodes are the child of parent node.


### Advantages:

* Decision trees are easy to explain. it results in a set of rules
* Simple to understand, interpret, and visualize.
* It follows the same approach as humans generally follow while ma king decisions.
* Data preparation is not much required.
* Interpretation of a complex decision tree model can be simplifie d by its visualizations.Even a naive person can understand logic.
* The number of hyper parameters to be tuned is almost null.
* It can handle numerical as well as categorical data.
* Non linear parameters has no impact on performance.

### Disadvantages:

* there is a high probability of overfitting in decision tree, whe n the algorithms capture\nnoise in the data.
* generally, it gives low prediction accuracy for a dataset as com pared to other machine learning algorithms.
* information gain in a decision tree with categorical variables g ives a biased response for attributes with greater no. of categories.
* calculations can become complex when there are many class labels
* high variance. the model can get unstable due to small variation s in data.
* low biased tree. highly complicated decision trees tends to have a low bias which makes it difficult for the model to work with new data.

### Assumptions we make while using decision tree :

* At the beginning, we consider the whole training set as the root.
* Attributes are assumed to be categorical for information gain and for gini index, attributes are assumed to be continuous.
* On the basis of attribute values records are distributed recursively.
* We use statistical methods for ordering attributes as root or internal node.



### Entropy (Slow coz multiple calculation required)

* Entropy is the measure of uncertainty of a random variable, it characterizes the impurity of an arbitrary collection ofexamples. the higher the entropy the more the informationcontent.

![entrophy.png](entrophy.png)





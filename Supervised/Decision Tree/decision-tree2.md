### $\large{\color{Blue}\underline{\mathcal{Decision\ Tree\ Practical}}}$


### $\large{\color{Purple}\underline{\textrm{The data}}}$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/fd303e94-8b44-4234-8a8b-8671c23e648e" width=50%/>
</p>


In the theory lectures we have already seen the different options available to us when building binary trees for example the 
* first thing we have to consider is the **type of tree** which we want to build we can either have **binary trees** or **multi way trees** depending upon the **branching factor** at each node
* another option available to us is the **impurity measure** used in this tutorial we will be looking at two different impurity measures which are **cross entropy** and the **Gini index**.
* Another option which we do not consider here is the **pruning technique** used.

### $\large{\color{Purple}\underline{\textrm{Multiway Split Using Cross-entrophy}}}$
To start with let us try and build a tree using multi-way splits and cross entropy as the impurity measure, the first thing that we have to do is to identify the root node this is done by considering each attribute in turn calculating the cross entropy value for that attribute and identifying the attribute which uses the lowest value let us start by considering the attribute age. (Refer

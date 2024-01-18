### ⬛ $\Large{\color{Blue}\underline{\mathcal{Decision\ Tree\ Practical}}}$




In the theory lectures we have already seen the different options available to us when building binary trees for example the 
* first thing we have to consider is the **type of tree** which we want to build we can either have **binary trees** or **multi way trees** depending upon the **branching factor** at each node
* another option available to us is the **impurity measure** used in this tutorial we will be looking at two different impurity measures which are **cross entropy** and the **Gini index**.
* Another option which we do not consider here is the **pruning technique** used.

### <ins>Cross Entrophy</ins>

$$\Large{\color{Purple} \mathrm{Cross\ Entropy} = - \sum_{k=1}^{K} \hat{p}\_{mk} \log \hat{p}\_{mk}}$$


* $\large{\color{Purple}S}$ represents the **data set** that entropy is calculated.
* $\large{\color{Purple}c}$ represents the **classes** in set $\large{\color{Purple}S}$
* $\large{\color{Purple}p(c)}$ represents the **proportion of data points** that belong to **class** $\large{\color{Purple}c}$ to the number of total data points in the set $\large{\color{Purple}S}$

### <ins>Gini Index</ins>

$$\Large{\color{Purple} \mathrm{Gini\ Index} = \sum_{k\neq k^{\prime}} \hat{p}\_{mk} \ \hat{p}\_{mk^{\prime}} = \sum_{k=1}^{K}  \hat{p}\_{mk} ( 1 - \hat{p}\_{mk})}$$


### $\large{\color{Purple}\underline{\textrm{The data}}}$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/fd303e94-8b44-4234-8a8b-8671c23e648e" width=50%/>
</p>

### 🔲 $\large{\color{Purple}\underline{\textrm{Multiway Split Using Cross-entrophy}}}$
To start with let us try and build a tree using **Multi-way splits** and **cross entropy** as the **impurity measure**, the first thing that we have to do is to identify the **root node** this is done by considering each **attribute** in turn calculating the **cross entropy value** for that **attribute** and **identifying the attribute** which uses the **lowest** value let us start by considering the attribute <ins><b>"age"</b></ins>. 

### ♠️ $\large{\color{Purple}age}$

From the table we observe that the attribute <ins><b>"age"</b></ins> can take on three distinct values which are <ins><b>youth</b></ins>, <ins><b>middle-aged</b></ins> and <ins><b>senior</b></ins>, going back to the formula for <ins><b>Cross Entropy</b></ins>. 

We see that for each node we need the proportion of class k observations in that node in case of a two class problem (yes, no)such as the one we are considering we can use the simpler expression 
– p x log p – (1- p) x (log 1 – p) 

where p is the proportion of observations for the positive class. Since, we need to calculate the cross entropy for an attribute with three distinct values we will have three components.

### $\large{\color{Purple}age \rightarrow youth}$
Let us first consider the value youth this is highlighted in the table we observe that out of the 14 different data points five observations have aged equals to youth among them two are belonging to the positive class and three belong to the negative class
   
<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/bacc1bd7-4759-4614-a639-9999e54f1dd1" width=50%/>
</p>


  ![image](https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ec7a1b36-6da7-4e72-b443-259b6bb776b2)

  ![image](https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/d7f7ea6a-f90c-4d6c-b29d-f2e66fe839bc)



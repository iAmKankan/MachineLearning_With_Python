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

### $\Large{\color{Purple}Example \\# 1 }$
### $\large{\color{Purple}\underline{\textrm{Multiway Split Using Cross-entrophy}}}$
To start with let us try and build a tree using **Multi-way splits** and **cross entropy** as the **impurity measure**, the first thing that we have to do is to identify the **root node** this is done by considering each **attribute** in turn calculating the **cross entropy value** for that **attribute** and **identifying the attribute** which uses the **lowest** value let us start by considering the attribute <ins><b>"age"</b></ins>. 


<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/f0884d38-f84d-45c0-a850-3b09a8dc0312" width=90%/>
  <br>
  <ins><b><i>The Data</i></b></ins>
</p>

### $\large{\color{Purple}Step \\# 1 }$
### ♠️ $\large{\color{Purple}age}$

From the table we observe that the attribute <ins><b>"age"</b></ins> can take on three distinct values which are <ins><b>youth</b></ins>, <ins><b>middle-aged</b></ins> and <ins><b>senior</b></ins>, going back to the formula for <ins><b>Cross Entropy</b></ins>. 

We see that for each node we need the proportion of class k observations in that node in case of a two class problem (yes, no)such as the one we are considering we can use the simpler expression 

$$\Large{\color{Purple}– p \log p (-(1- p) \log (1 – p)) }$$

Where p is the proportion of observations for the positive class. Since, we need to calculate the cross entropy for an attribute with three distinct values we will have three components.

### $\large{\color{Purple}\textrm{age} \rightarrow \textrm{youth, middle-aged, senor}}$
Let us first consider the value youth this is highlighted in the table we observe that out of the 14 different data points five observations have aged equals to youth among them two are belonging to the positive class and three belong to the negative class
   
<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/2ab55b6e-bec0-4ddd-bb1a-370efbe0e6d2" width=30%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6b6cabc2-d78d-403e-9866-9da4648072ac" width=30%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/35b4061c-17f8-495b-b66b-8390c410e728" width=30%/>
</p>

Using this information we have  $\large{\color{Purple}-(2 / 5) * log (2 / 5)}$ that is the proportion of observation belonging to the positive class and  $\large{\color{Purple}- (3 / 5) * (log 3 / 5)}$ for the negative class this expression is multiplied by the ratio 5 :14 which indicates which is a weight on the which is a normalizing factor since five out of the14 data points had aged equals to youth continuing with this manner we take up the next value that is age equals two middle-aged and observe that among the 14 there are 4 points where age equal to middle-aged and for all of them buys computer equals two years that is they all belong to the positive class.

This gives us the second component as you can see we do not necessarily need to calculate this but we have put it there just for your reference the final component comes when we consider age is equals to senior again there are 5 points with age is equals to senior of them we observe that three belong to the positive class and to belong 2 the negative class putting it all together we get a value of cross entropy. that all logarithms used here are using the base 2.

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{age}(D)}&:& (\dfrac{5}{14})(- \dfrac{2}{5} \log_2 \dfrac{2}{5} - \dfrac{3}{5} \log_2 \dfrac{3}{5}) \\
& &+(\dfrac{4}{14})(- \dfrac{4}{4} \log_2 \dfrac{4}{4} - \dfrac{0}{4} \log_2 \dfrac{0}{4})\\
& &+(\dfrac{5}{14})(-\dfrac{3}{5} \log_2 \dfrac{3}{5} - \dfrac{2}{5} \log_2 \dfrac{2}{5})\\
& &=0.6935
\end{matrix}}$$

### ♠️ $\large{\color{Purple}income}$
We now consider the attribute income and find the cross entropy width next we find the cross entropy for the attribute student and a cross and trouble for the credit rating note that here we have only two components because both of these are binary valued.


$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{income}(D)} &:& (\dfrac{4}{14})(- \dfrac{3}{4} \log_2 \dfrac{3}{4} - \dfrac{1}{4} \log_2 \dfrac{1}{4}) \\
& &+(\dfrac{6}{14})(- \dfrac{4}{6} \log_2 \dfrac{4}{6} - \dfrac{2}{6} \log_2 \dfrac{2}{6})\\
& &+(\dfrac{4}{14})(-\dfrac{2}{4} \log_2 \dfrac{2}{4} - \dfrac{2}{4} \log_2 \dfrac{2}{4})\\
& &=0.9111
\end{matrix}}$$

### ♠️ $\large{\color{Purple}student}$

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{student}(D)} &:& (\dfrac{7}{14})(- \dfrac{3}{7} \log_2 \dfrac{3}{7} - \dfrac{4}{7} \log_2 \dfrac{4}{7}) \\
& &+(\dfrac{7}{14})(-\dfrac{6}{7} \log_2 \dfrac{6}{7} - \dfrac{1}{7} \log_2 \dfrac{1}{7})\\
& &=0.7885
\end{matrix}}$$

### ♠️ $\large{\color{Purple}credit-rating}$

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{credit-rating}(D)} &:& (\dfrac{8}{14})(- \dfrac{6}{8} \log_2 \dfrac{6}{8} - \dfrac{2}{8} \log_2 \dfrac{2}{8}) \\
& &+(\dfrac{6}{14})(-\dfrac{3}{6} \log_2 \dfrac{3}{6} - \dfrac{3}{6} \log_2 \dfrac{3}{6})\\
& &=0.8922
\end{matrix}}$$

### The final Cross-entrophy results for each features:
Finally we compare each of the cross entropy values and in this case observed that the attribute age gives the lowest cross entropy value and hence is the optimal attribute to use as the **root** of the our decision tree.

$$\Large{\color{Purple}
\begin{matrix*}[l] 
Cross-Entrophy_{age}(D) = 0.6935 \\
Cross-Entrophy_{income}(D) = 0.9111 \\
Cross-Entrophy_{student}(D) = 0.7885 \\
Cross-Entrophy_{credit-rating}(D) = 0.8922\\
\end{matrix*}}$$



### $\large{\color{Purple}\underline{\textrm{Drawing the Tree}}}$
Thus we obtain the partial decision tree with age as the root attribute and three branches corresponding to the three distinct values that the attribute age can take note that the middle-aged that is the branch where a age equals two middle-aged has been labeled with yes indicating that this is a leaf node where any observation following along this branch will be labeled yes this is because if we go back to the table we observe that when age equals to middle-aged buys computer equals to yes.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/05a7e0fa-1ec6-40f3-bce6-1a4f8fa9b5cf" width=60%/>
</p>

Thus along this branch of the tree there is no need to further grow the tree since from the training data given to us we can directly conclude that if we observe age to be middle-aged then we can label the class and the observation as positive that is the person will buy a computer. Now we have created this partial decision tree so how do we proceed? Essentially it is a recursive process we started at the root node we were able to find the root node to be the attribute age. Now along each of the remaining branches where we have not found the note to be a leaf node we have to repeat the same process. So let us first look at the branch is equals to youth we have already considered the attribute age, so there are three attributes left to us using a process similar to what we have just seen we try to identify the best attribute to use at this position.

### $\large{\color{Purple}Step \\# 2 }$
##### Now we have created this partial decision tree so how do we proceed? 
Essentially it is a **recursive process** we started at the **root node** we were able to find the root node to be the attribute **age**. Now along each of the remaining branches where we have not found the note to be a leaf node we have to repeat the same process. So let us first look at the branch is equals to youth we have already considered the attribute age, so there are three attributes left to us using a process similar to what we have just seen we try to identify the best attribute to use at this position.


So we consider the cross entropy of income where age equals to youth, now we are not now we will not be considering the entire data set but will consider the restricted data set where age equals to youth. This is illustrated in this table where we have crossed out all observations where age is not youth so essentially we repeat the same entire process with this restricted data set note that the attribute age has already been considered so we are left with the remain three attributes and these are the values that are to be considered.


<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/319865bb-7502-4c3e-a9cc-2ba156dd2ce9" width=60%/>
</p>

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{income}(age=youth)}&:& (\dfrac{1}{5})(- \dfrac{1}{1} \log_2 \dfrac{1}{1} - \dfrac{0}{1} \log_2 \dfrac{0}{1}) \\
& &+(\dfrac{2}{5})(- \dfrac{1}{2} \log_2 \dfrac{1}{2} - \dfrac{1}{2} \log_2 \dfrac{1}{2})\\
& &+(\dfrac{2}{5})(-\dfrac{0}{2} \log_2 \dfrac{0}{2} - \dfrac{2}{2} \log_2 \dfrac{2}{2})\\
& &=0.4
\end{matrix}}$$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ff7bc330-8f76-4d89-ad03-0bae110b505e" width=60%/>
</p>

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{student}(age=youth)}&:& (\dfrac{3}{5})(- \dfrac{0}{3} \log_2 \dfrac{0}{3} - \dfrac{3}{3} \log_2 \dfrac{3}{3}) \\
& &+(\dfrac{2}{5})(- \dfrac{2}{2} \log_2 \dfrac{2}{2} - \dfrac{0}{2} \log_2 \dfrac{0}{2})\\
& &=0.0
\end{matrix}}$$

Thus we have cross entropy of income when age equals to youth you can go back and verify that these are the values you will obtain next we have cross entropy of student when they is equal to youth here we observe that the cross entropy is actually 0 going back to the table we see that in a equals to youth and student is no bias computer is no and when student is yes buy computers yes so this leads us to a pure leaf we can go ahead and calculate the cross entropy for credit rating as well when age is equals to youth but since we will not get a value less than 0. We can stop the process here and get the partial tree where we have selected the attribute student with the least value of cross entropy

###  The final result of "age" = "youth"

$$\Large{\color{Purple}\begin{matrix}
Cross-Entrophy_{income}(age=youth) & = & 0.4 \\
Cross-Entrophy_{student}(age=youth) & = & 0.0 \\
\end{matrix}}$$

### Drawing the subtree

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/3974cd45-5d10-446d-9199-dda9197a4801" width=60%/>
</p>

As you can see we have labeled the branches $\large{\color{purple}yes}$ and $\large{\color{purple}no}$ because these are $\large{\color{green}leaf\ nodes}$ which are **pure** there is $\large{\color{purple}no}$ mixture, now as you can see we have this branch this branch in this branch are all $\large{\color{green}leaf\ nodes}$ so last the remaining at branch to consider is when age is equals to senior again we look at the table where we discard all observations where it is not senior and follow the same calculations.

### $\large{\color{Purple}Step \\# 3 }$
### $\large{\color{Purple}\textrm{age=senior} }$






<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/b73c2de3-ccf6-41c0-a49c-25eec95387bc" width=60%/>
</p>

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{income}(age=senior)}&:& (\dfrac{2}{5})(- \dfrac{1}{2} \log_2 \dfrac{1}{2} - \dfrac{1}{2} \log_2 \dfrac{1}{2}) \\
& &+(\dfrac{3}{5})(- \dfrac{2}{3} \log_2 \dfrac{2}{3} - \dfrac{1}{3} \log_2 \dfrac{1}{3})\\
& &=0.9510
\end{matrix}}$$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/aa3515f0-b4af-48db-a4a9-1868622c76ea" width=60%/>
</p>


$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{student}(age=senior)}&:& (\dfrac{2}{5})(- \dfrac{1}{2} \log_2 \dfrac{1}{2} - \dfrac{1}{2} \log_2 \dfrac{1}{2}) \\
& &+(\dfrac{3}{5})(- \dfrac{2}{3} \log_2 \dfrac{2}{3} - \dfrac{1}{3} \log_2 \dfrac{1}{3})\\
& &=0.9510
\end{matrix}}$$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6cef56a1-808e-4a8e-8222-a8367a38d0c9" width=60%/>
</p>


$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{credit-rating}(age=senior)}&:& (\dfrac{3}{5})(- \dfrac{3}{3} \log_2 \dfrac{0}{3} - \dfrac{}{3} \log_2 \dfrac{0}{3}) \\
& &+(\dfrac{2}{5})(- \dfrac{0}{2} \log_2 \dfrac{0}{2} - \dfrac{2}{2} \log_2 \dfrac{2}{2})\\
& &=0.0
\end{matrix}}$$


<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ccdc236b-8026-4d3f-809f-f32fd2bcef86" width=60%/>
</p>

### $\Large{\color{Purple}Example \\# 2 }$
### $\large{\color{Purple}\underline{\textrm{Binary Split Using Gini index}}}$
For binary splits, for the same attribute, we have to compute impurity multiple times for the different subsets of the attributes value

As mentioned previously, for a binary outcome, to reduce the number of partitions to be considered, we order the values according to the proportion belonging to the positive class.




### Binary Split using Gini index
For binary splits, for the same attribute, we have to compute impurity multiple times for the different subsets of the attributes value

As mentioned previously, for a binary outcome, to reduce the number of partitions to be considered, we order the values according to the proportion belonging to the positive class.


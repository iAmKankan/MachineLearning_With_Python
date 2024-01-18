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

$$\Large{\color{Purple}– p \log p (-(1- p) \log (1 – p)) }$$

Where p is the proportion of observations for the positive class. Since, we need to calculate the cross entropy for an attribute with three distinct values we will have three components.

### $\large{\color{Purple}\textrm{age} \rightarrow \textrm{youth, middle-aged, senor}}$
Let us first consider the value youth this is highlighted in the table we observe that out of the 14 different data points five observations have aged equals to youth among them two are belonging to the positive class and three belong to the negative class
   
<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/bacc1bd7-4759-4614-a639-9999e54f1dd1" width=30%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ec7a1b36-6da7-4e72-b443-259b6bb776b2" width=30%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/d7f7ea6a-f90c-4d6c-b29d-f2e66fe839bc" width=30%/>
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



### 🔲 $\large{\color{Purple}\underline{\textrm{Drawing the Tree}}}$
Thus we obtain the partial decision tree with age as the root attribute and three branches corresponding to the three distinct values that the attribute age can take note that the middle-aged that is the branch where a age equals two middle-aged has been labeled with yes indicating that this is a leaf node where any observation following along this branch will be labeled yes this is because if we go back to the table we observe that when age equals to middle-aged buys computer equals to yes.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/1ee906f0-62d8-4483-85a7-d2d4f4e29472" width=50%/>
</p>

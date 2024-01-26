### ⬛ $\Large{\color{Blue}\underline{\mathcal{Decision\ Tree\ Practical}}}$
In the theory lectures we have already seen the different options available to us when building binary trees for example the 
* First thing we have to consider is the **type of tree** which we want to build we can either have **binary trees** or **multi way trees** depending upon the **branching factor** at each node
* another option available to us is the **impurity measure** used in this tutorial we will be looking at two different impurity measures which are **cross entropy** and the **Gini index**.
* Another option which we do not consider here is the **pruning technique** used.

### $\large{\color{Purple}\underline{\textrm{Cross Entrophy}}}$

$$\Large{\color{Purple} \mathrm{Cross\ Entropy} = - \sum_{k=1}^{K} \hat{p}\_{mk} \log \hat{p}\_{mk}}$$


* $\large{\color{Purple}S}$ represents the **data set** that entropy is calculated.
* $\large{\color{Purple}c}$ represents the **classes** in set $\large{\color{Purple}S}$
* $\large{\color{Purple}p(c)}$ represents the **proportion of data points** that belong to **class** $\large{\color{Purple}c}$ to the number of total data points in the set $\large{\color{Purple}S}$

### $\large{\color{Purple}\underline{\textrm{Gini Index}}}$

$$\Large{\color{Purple} \mathrm{Gini\ Index} = \sum_{k\neq k^{\prime}} \hat{p}\_{mk} \ \hat{p}\_{mk^{\prime}} = \sum_{k=1}^{K}  \hat{p}\_{mk} ( 1 - \hat{p}\_{mk})}$$

### $\Large{\color{Purple}Example \\# 1 }$
### $\large{\color{Purple}\underline{\textrm{Multiway Split Using Cross-entrophy}}}$
Let's build a tree using <ins><b>Multi-way splits</b></ins> using <ins><b>cross entropy</b></ins> as the <ins><b>impurity measure</b></ins>-
* The first thing that we have to do is to identify the <ins><b>root node</b></ins> this is done by findout the <ins><b>lowest cross entropy value</b></ins> with in all <ins><b>attributes</b></ins>.
* The <ins><b>attribute</b></ins> with the <ins><b>lowest cross entropy</b></ins> value would be the <ins><b>root</b></ins>.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/f0884d38-f84d-45c0-a850-3b09a8dc0312" width=90%/>
  <br>
  <ins><b><i>"Buying Computer" Data</i></b></ins>
</p>

### $\large{\color{Purple}Step \\# 1 }$
 going back to the formula for <ins><b>Cross Entropy</b></ins>. 

We see that for each node we need the proportion of class k observations in that node in case of a two class problem (yes, no)such as the one we are considering we can use the simpler expression 

$$\Large{\color{Purple}– (p_{(+ve)} \log_2 p_{(+ve)}) – (p_{(-ve)} \log_2 p_{(-ve)}) }$$

Where p is the proportion of observations for the positive class. Since, we need to calculate the cross entropy for an attribute with three distinct values we will have three components.

### ♠️ $\large{\color{Purple}\underline{\textrm{age} \Rightarrow \textrm{youth, middle-aged, senior}}}$
From the table we observe that the attribute <ins><b>"age"</b></ins> can take on three distinct values which are <ins><b>youth</b></ins>, <ins><b>middle-aged</b></ins> and <ins><b>senior</b></ins>,

### $\large{\color{Purple}\underline{\textrm{age} \Rightarrow \textrm{youth}}}$
Let us first consider the value youth this is highlighted in the table we observe that out of the **14** different data points **5 observations** have **aged equals to youth** among them **2 observations** are belonging to the **positive class** and **3 observations** belong to the **negative class**

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6de873aa-1bb2-464e-a3b2-fa9a25151db4" width=65%/>
  <br>
  <ins><b><i>"age" = "youth"</i></b></ins>
</p>

### Total $\large{\color{purple}5}$ observations are in $\large{\color{purple}\textrm{"age" = "youth"}}$
* $\large{\color{purple}2}$ of the observations are in  $\large{\color{purple}\textrm{"buys\\_computer" = "yes"}}$
* $\large{\color{purple}3}$ of the observations are in $\large{\color{purple}\textrm{"buys\\_computer" = "no"}}$
   
### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "age" = "youth":}}$
* $\large{\color{Purple}-(2 / 5) * \log (2 / 5)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (3 / 5) * \log (3 / 5)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(5 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **5** out of the **14** data points had **'aged' = 'youth'** continuing with this manner.

$$\Large{\color{Purple} \textrm{'youth'} = (\underbrace{\dfrac{5}{14}}\_{\textrm{'youth' in dataset}})(- \underbrace{\dfrac{2}{5} \log_2 \dfrac{2}{5}}\_{\textrm{+ve class in 'youth'}} - \underbrace{\dfrac{3}{5} \log_2 \dfrac{3}{5}}\_{\textrm{-ve class in 'youth'}})
}$$  


### $\large{\color{Purple}\underline{\textrm{age} \Rightarrow \textrm{middle-aged}}}$
Let us first consider the value youth this is highlighted in the table we observe that out of the **14** different data points **4 observations** have **aged equals to middle-aged** among them all **4 observations** are belonging to the **positive class**.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6070307a-e410-435a-8a27-b10d3b4c86df" width=65%/>
  <br>
  <ins><b><i>"age" = "middle-aged"</i></b></ins>
</p>

### Total $\large{\color{purple}4}$ observations are in $\large{\color{purple}\textrm{"age" = "middle-aged"}}$
* $\large{\color{purple}4}$ of the observations are in  $\large{\color{purple}\textrm{"buys\\_computer" = "yes"}}$
* $\large{\color{purple}0}$ of the observations are in  $\large{\color{purple}\textrm{"buys\\_computer" = "no"}}$
  
### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "age" = "middle-aged":}}$
* $\large{\color{Purple}-(4 / 4) * \log (4 / 4)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (0 / 4) * \log (0 / 4)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(4 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **4** out of the **14** data points had **'aged' = 'middle-aged'** continuing with this manner.

$$\Large{\color{Purple} \textrm{'middle\\_aged'}=(\underbrace{\dfrac{4}{14}}\_{\textrm{'middle\\_aged' in dataset}})(- \underbrace{\dfrac{4}{4} \log_2 \dfrac{4}{4}}\_{\textrm{+ve class in 'middle\\_aged'}} - \underbrace{\dfrac{0}{4} \log_2 \dfrac{0}{4}}\_{\textrm{-ve class in 'middle\\_aged'}})
}$$ 


### $\large{\color{Purple}\underline{\textrm{age} \Rightarrow \textrm{senior}}}$
Let us consider the value youth this is highlighted in the table we observe that out of the **14** different data points **5 observations** have **aged equals to senior** among them  **3 observations** are belonging to the **positive class** and **2 observations** are belonging to the **negetive class**.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/73c7cf6b-18ac-4f4b-b25e-44bf4d325247" width=65%/>
  <br>
  <ins><b><i>"age" = "senior"</i></b></ins>
</p>

### Total $\large{\color{purple}5}$ observations are in $\large{\color{purple}\textrm{"age" = "senior"}}$
* $\large{\color{purple}3}$ of the observations  $\large{\color{purple}\textrm{"buys\\_computer" = "yes"}}$
* $\large{\color{purple}2}$ of the observations  $\large{\color{purple}\textrm{"buys\\_computer" = "no"}}$
  
### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "age" = "senior":}}$
* $\large{\color{Purple}-(3 / 5) * \log (3 / 5)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (2 / 5) * \log (2 / 5)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(5 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **5** out of the **14** data points had **'aged' = 'senior'** continuing with this manner.

$$\Large{\color{Purple} \textrm{'senior'}=(\underbrace{\dfrac{5}{14}}\_{\textrm{'senior' in dataset}})(-\underbrace{\dfrac{3}{5} \log_2 \dfrac{3}{5}}\_{\textrm{+ve class in 'senior'}} - \underbrace{\dfrac{2}{5} \log_2 \dfrac{2}{5}}\_{\textrm{-ve class in 'senior'}})
}$$ 


### ⚛️ By adding up all three Cross entrophy values of the attribute "age" we get the following-

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(age)}(D)}&:& (\dfrac{5}{14})(- \dfrac{2}{5} \log_2 \dfrac{2}{5} - \dfrac{3}{5} \log_2 \dfrac{3}{5}) \\
& &+(\dfrac{4}{14})(- \dfrac{4}{4} \log_2 \dfrac{4}{4} - \dfrac{0}{4} \log_2 \dfrac{0}{4})\\
& &+(\dfrac{5}{14})(-\dfrac{3}{5} \log_2 \dfrac{3}{5} - \dfrac{2}{5} \log_2 \dfrac{2}{5})\\
& &=0.6935
\end{matrix}}$$


#### For 'age'= 'middle_aged' we have -
 we take up the next value that is 'age' = 'middle-aged' and observe that among the 14 there are 4 points where age equal to middle-aged and for all of them buys computer equals two years that is they all belong to the positive class.

This gives us the second component as you can see we do not necessarily need to calculate this but we have put it there just for your reference the final component comes when we consider age is equals to senior again there are 5 points with age is equals to senior of them we observe that three belong to the positive class and to belong 2 the negative class putting it all together we get a value of cross entropy. that all logarithms used here are using the base 2.

We now consider the attribute income and find the cross entropy width next we find the cross entropy for the attribute student and a cross and trouble for the credit rating note that here we have only two components because both of these are binary valued.

### ♠️ $\large{\color{Purple}\underline{\textrm{income} \Rightarrow \textrm{high, medium, low}}}$
From the table we observe that the attribute <ins><b>"income"</b></ins> can take on three distinct values which are <ins><b>high</b></ins>, <ins><b>medium</b></ins> and <ins><b>low</b></ins>,

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6edacd46-1834-4d67-9977-561d4854b9af" width=33%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/c1827ea5-ef06-4c47-84b6-2eaeacc5badb" width=33%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/a1c4a929-3b31-4011-bf9f-128b6350f6f3" width=33%/>
  <br>
  <ins><b><i>"income" = "high"</i></b></ins>, <ins><b><i>"income" = "medium"</i></b></ins>, <ins><b><i>"income" = "low"</i></b></ins>
</p>

### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "income" = "high":}}$
* $\large{\color{Purple}-(2 / 4) * \log (2 / 4)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (2 / 4) * \log (2 / 4)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(4 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **4** out of the **14** data points had **"income" = "high"** continuing with this manner.

  ### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "income" = "medium":}}$
* $\large{\color{Purple}-(4 / 6) * \log (4/ 6)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (2 / 6) * \log (2 / 6)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(6 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **6** out of the **14** data points had **"income" = "medium"** continuing with this manner.

  ### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "income" = "low":}}$
* $\large{\color{Purple}-(3 / 4) * \log (3/ 4)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (1 / 4) * \log (1 / 4)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(4 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **4** out of the **14** data points had **"income" = "low"** continuing with this manner.

### ⚛️ By adding up all three Cross entrophy values of the attribute "income" we get the following-
  
$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(income)}(D)} &:& (\dfrac{4}{14})(- \dfrac{3}{4} \log_2 \dfrac{3}{4} - \dfrac{1}{4} \log_2 \dfrac{1}{4}) \\
& &+(\dfrac{6}{14})(- \dfrac{4}{6} \log_2 \dfrac{4}{6} - \dfrac{2}{6} \log_2 \dfrac{2}{6})\\
& &+(\dfrac{4}{14})(-\dfrac{2}{4} \log_2 \dfrac{2}{4} - \dfrac{2}{4} \log_2 \dfrac{2}{4})\\
& &=0.9111
\end{matrix}}$$

### ♠️ $\large{\color{Purple}\underline{\textrm{student} \Rightarrow \textrm{no, yes}}}$
From the table we observe that the attribute <ins><b>"student"</b></ins> can take on 2 distinct values which are <ins><b>yes</b></ins> and <ins><b>no</b></ins>.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/051bea86-a0a7-4a27-800a-60c4e504f201" width=40%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ce75a95a-b14b-4191-aa55-a897a9ec5ffd" width=40%/>
  <br>
  <ins><b><i>"student" = "no"</i></b></ins> , <ins><b><i>"student" = "yes"</i></b></ins>,
</p>

 ### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "student" = "no":}}$
* $\large{\color{Purple}-(3 / 7) * \log (3/ 7)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (4 / 7) * \log (4 / 7)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(7 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **7** out of the **14** data points had **"student" = "no"** continuing with this manner.
  
 ### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "student" = "yes":}}$
* $\large{\color{Purple}-(6 / 7) * \log (6/ 7)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (1 / 7) * \log (1 / 7)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(7 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **7** out of the **14** data points had **"student" = "yes"** continuing with this manner.

### ⚛️ By adding up all two Cross entrophy values of the attribute "student" we get the following-
    
$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(student)}(D)} &:& (\dfrac{7}{14})(- \dfrac{3}{7} \log_2 \dfrac{3}{7} - \dfrac{4}{7} \log_2 \dfrac{4}{7}) \\
& &+(\dfrac{7}{14})(-\dfrac{6}{7} \log_2 \dfrac{6}{7} - \dfrac{1}{7} \log_2 \dfrac{1}{7})\\
& &=0.7885
\end{matrix}}$$

### ♠️ $\large{\color{Purple}\underline{\textrm{credit-rating} \Rightarrow \textrm{fair, excellent}}}$
From the table we observe that the attribute <ins><b>"credit-rating"</b></ins> can take on three distinct values which are <ins><b>fair</b></ins>, <ins><b>excellent</b></ins> .


<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/28ce1f19-da4a-4509-9fe5-6c0e4dbe3b18" width=40%/>
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/598bd61e-dea7-4b5b-b815-82b161f81a0a" width=40%/>
  <br>
  <ins><b><i>"credit-rating" = "fair"</i></b></ins> , <ins><b><i>"credit-rating" = "excellent"</i></b></ins>,
</p>



### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "credit-rating" = "fair":}}$
* $\large{\color{Purple}-(6 / 8) * \log (6/ 8)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (2 / 8) * \log (2 / 8)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(8 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **8** out of the **14** data points had **"credit-rating" = "fair"** continuing with this manner.

### $\large{\color{Purple}\textrm{Cross-Entrophy calculation for attribute "credit-rating" = "excellent":}}$
* $\large{\color{Purple}-(3 / 6) * \log (3/ 6)}$ that is the **proportion of observation** belonging to the **positive class** and
* $\large{\color{Purple}- (3 / 6) * \log (3 / 6)}$ that is the **proportion of observation** belonging to the **negative class**
* Above two expressions need to **multiplied** by the **ratio** $\large{\color{Purple}(6 /14) }$ which indicates which is a **weight** on the which is a **normalizing factor** since **6** out of the **14** data points had **"credit-rating" = "excellent"** continuing with this manner.

### ⚛️ By adding up all two Cross entrophy values of the attribute "credit-rating" we get the following-

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(credit-rating)}(D)} &:& (\dfrac{8}{14})(- \dfrac{6}{8} \log_2 \dfrac{6}{8} - \dfrac{2}{8} \log_2 \dfrac{2}{8}) \\
& &+(\dfrac{6}{14})(-\dfrac{3}{6} \log_2 \dfrac{3}{6} - \dfrac{3}{6} \log_2 \dfrac{3}{6})\\
& &=0.8922
\end{matrix}}$$

### ❇️  The final Cross-entrophy results for each Attributes:
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

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(income)}(age=youth)}&:& (\dfrac{1}{5})(- \dfrac{1}{1} \log_2 \dfrac{1}{1} - \dfrac{0}{1} \log_2 \dfrac{0}{1}) \\
& &+(\dfrac{2}{5})(- \dfrac{1}{2} \log_2 \dfrac{1}{2} - \dfrac{1}{2} \log_2 \dfrac{1}{2})\\
& &+(\dfrac{2}{5})(-\dfrac{0}{2} \log_2 \dfrac{0}{2} - \dfrac{2}{2} \log_2 \dfrac{2}{2})\\
& &=0.4
\end{matrix}}$$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ff7bc330-8f76-4d89-ad03-0bae110b505e" width=60%/>
</p>

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(student)}(age=youth)}&:& (\dfrac{3}{5})(- \dfrac{0}{3} \log_2 \dfrac{0}{3} - \dfrac{3}{3} \log_2 \dfrac{3}{3}) \\
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

$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(income)}(age=senior)}&:& (\dfrac{2}{5})(- \dfrac{1}{2} \log_2 \dfrac{1}{2} - \dfrac{1}{2} \log_2 \dfrac{1}{2}) \\
& &+(\dfrac{3}{5})(- \dfrac{2}{3} \log_2 \dfrac{2}{3} - \dfrac{1}{3} \log_2 \dfrac{1}{3})\\
& &=0.9510
\end{matrix}}$$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/aa3515f0-b4af-48db-a4a9-1868622c76ea" width=60%/>
</p>


$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(student)}(age=senior)}&:& (\dfrac{2}{5})(- \dfrac{1}{2} \log_2 \dfrac{1}{2} - \dfrac{1}{2} \log_2 \dfrac{1}{2}) \\
& &+(\dfrac{3}{5})(- \dfrac{2}{3} \log_2 \dfrac{2}{3} - \dfrac{1}{3} \log_2 \dfrac{1}{3})\\
& &=0.9510
\end{matrix}}$$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6cef56a1-808e-4a8e-8222-a8367a38d0c9" width=60%/>
</p>


$$\Large{\color{Purple}\begin{matrix}\underline{Cross-Entrophy_{(credit-rating)}(age=senior)}&:& (\dfrac{3}{5})(- \dfrac{3}{3} \log_2 \dfrac{0}{3} - \dfrac{}{3} \log_2 \dfrac{0}{3}) \\
& &+(\dfrac{2}{5})(- \dfrac{0}{2} \log_2 \dfrac{0}{2} - \dfrac{2}{2} \log_2 \dfrac{2}{2})\\
& &=0.0
\end{matrix}}$$


<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ccdc236b-8026-4d3f-809f-f32fd2bcef86" width=60%/>
</p>



Here each of the **leaf node** is a **pure node** in case we did not get a **cross entropy** value of **0** let us say we have a different value cross entropy here we would again continue the process and the last situation is when we have exhausted all attributes available to us and we still do not have a **pure leaf** what do we do then essentially let us say when we follow this branch there were five points of which three were positive and two were negative then this would have been labeled yes. 

Because the majority of the data points have a positive Cubs have a positive belong to the positive class fortunately for us in this example we have obtained all leaf nodes as pure but this will always this will not always be the case.


### $\Large{\color{Purple}Example \\# 2 }$
### $\large{\color{Purple}\underline{\textrm{Binary Split Using Gini index}}}$
For binary splits, for the same attribute, we have to compute impurity multiple times for the different subsets of the attributes value

As mentioned previously, for a binary outcome, to reduce the number of partitions to be considered, we order the values according to the proportion belonging to the positive class.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/f0884d38-f84d-45c0-a850-3b09a8dc0312" width=90%/>
  <br>
  <ins><b><i>"Buying Computer" Data</i></b></ins>
</p>

### $\large{\color{Purple}\underline{\textrm{Gini Index}}}$

$$\Large{\color{Purple} \mathrm{Gini\ Index} = \sum_{k\neq k^{\prime}} \hat{p}\_{mk} \ \hat{p}\_{mk^{\prime}} = \sum_{k=1}^{K}  \hat{p}\_{mk} ( 1 - \hat{p}\_{mk})}$$


### Positive class proportion for "age" attribute:
* "youth" = 2/5
* "middle_aged" = 1
* "senior" = 3/5

### Possible Split points:
 * $\large{\color{purple}\\{youth\\}, \\{senior, middleaged\\}}$
 * $\large{\color{purple}\\{youth, senior\\}, \\{middleaged\\}}$
 

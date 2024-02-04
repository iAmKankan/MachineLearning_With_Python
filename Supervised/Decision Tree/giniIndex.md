
### 🔲 $\large{\color{Purple}\underline{\textrm{Gini Impurity:}}}$ 

<ins><b>Gini impurity is the probability of incorrectly classifying random data point in the dataset if it were labeled based on the class distribution of the dataset</b></ins>. 

Similar to **entropy**, if set, S, is pure—i.e. belonging to one class) then, its impurity is zero. This is denoted by the following formula: 

$$\Large{\color{Purple}\textrm{Gini Impurity} = 1 -\sum_i (p_i)^2}$$


<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/0f55d05f-fd02-4774-bd36-130065404532" width=70%/>
  <br>
  <ins><b><i> school-boy data</i></b></ins>
</p>


### $\large {\color{Purple}Step 1 \\# }$ 
#### Compute the <ins>Gini Index</ins> for the overall collection of training examples.

 ###  ♠️ $\large{\color{Purple}decision \rightarrow \\{ movie, tennis, stay\\_in , shopping \\} }$
The **output variable**, **target variable** or $\large{\color{Purple}y}$ as $\large{\color{Purple}decision}$-
* The data has **6 instances of 'movie'**, **2 instances of 'tennis'**, **1 instance of 'sta-in'** and **1 of 'shopping'**.

$$\Large {\color{purple}Gini(S)=1-\[ (6/10) ^ 2 + (2/10) ^ 2 + (1/10) ^ 2 + (1/10) ^ 2 \]=0.58}$$

###  ♠️ $\large{\color{Purple}money \rightarrow \\{rich, poor \\} }$
Attribute <ins><b>money</b></ins> has two possible values of **7 instances of 'rich'** and **3 instances of 'poor'**.
* For $\large{\color{purple}money = poor}$, there are **3** examples with $\large{\color{purple}decision = movie}$.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ca1fc073-0523-4d14-9b0d-d0d2f3393ee4" width=40%/>
  <br>
  <ins><b><i></i></b></ins>
</p>

$$\Large {\color{purple} Gini (S) = 1 - [(3/3) ^ 2] = 0}$$

*  For $\large{\color{purple}money = rich}$ , there are **2** examples with $\large{\color{purple}decision = tennis}$ , **3** examples with $\large{\color{purple}decision = movie}$ , **1** example with $\large{\color{purple}decision = stay\\_in}$ and  **1** example with $\large{\color{purple}decision = shopping}$ .

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6f3d1ba2-3d1d-4b32-9d2d-a2e944fb1c5d" width=40%/>
  <br>
  <ins><b><i></i></b></ins>
</p>

$$\Large {\color{purple} Gini (S) = 1 - \[ (2/7) ^ 2 + (3/7) ^ 2 + (1/7) ^ 2 + (1/7) ^ 2 \] = 0.694}$$

$$\Large {\color{purple}Weighted\ Average(Money) =0*( 3 10 )+0.69 \dot 4(7/10) = 0.486}$$

###  ♠️ $\large{\color{Purple}parents \rightarrow \\{yes, no \\} }$
Attribute <ins><b>parents</b></ins> has two possible values of **5 instances of 'yes'** and **5 instances of 'no'**.
* For $\large{\color{purple}parents = yes}$ there are all **5** examples with $\large{\color{purple}decision = movie}$.

$$\Large {\color{purple}Gini (S) = 1 - \[(5/5) ^ 2\] = 0}$$

* For $\large{\color{purple}parents = no}$ , there are **2** examples with $\large{\color{purple}decision = tennis}$, **1** example with $\large{\color{purple}decision = stay\\_in}$, **1** example with $\large{\color{purple}decision = shopping}$ and **1** example with $\large{\color{purple}decision = movie}$.
  
$$\Large {\color{purple}Gini (S) = 1 - \[(2/5) ^ 2 + (1/5) ^ 2 + (1/5) ^ 2 + (1/5) ^ 2\] = 0.72}$$

$$\Large {\color{purple}Weighted\ Average(Parents) = 0*( 5 10 )+ \[ 0.72(5/10) = 0.36 \]}$$

###  ♠️ $\large{\color{Purple}weather \rightarrow \\{sunny, rainy, windy \\} }$
Attribute <ins><b>weather</b></ins> has 3 possible values of **3 instances of 'sunny'**, **3 instances of 'rainy'** and **4 instances of 'windy'**.

* For $\large{\color{purple}weather = sunny}$ , there are **2** examples with $\large{\color{purple}decision = movie}$ and **1** with $\large{\color{purple}decision = tennis}$.

$$\Large {\color{purple} Gini(Sunny)= 1 - \[(2/3) ^ 2 + (1/3) ^ 2\] = 0.44}$$

* For $\large{\color{purple}weather = rainy}$, there are **2** examples with $\large{\color{purple}decision = movie}$ and **1** example with $\large{\color{purple}decision = stay\\_in}$

$$\Large {\color{purple}Gini(Rainy)= 1 - \[(2/3) ^ 2 + (1/3) ^ 2\] = 0.44 }$$

* For $\large{\color{purple}weather = windy}$ , there are **3** examples with $\large{\color{purple}decision = movie}$ and **1** example with $\large{\color{purple}decision = shopping}$

$$\Large {\color{purple}Gini(Windy)= 1 - \[(3/4) ^ 2 + (1/4) ^ 2\] = 0.375}$$

$$\Large {\color{purple} Weighted\ Average(Weather) = 0.444(3/10) + 0.444(3/10) + 0.375(4/10) = 0.416}$$

### $\large {\color{Purple}\underline{\textrm{Final Gini-Index of }} Step 1 \\# }$ 

- For <ins><b>weather</ins></b> - Gini Index: **0.416**
- For <ins><b>parents</ins></b> - Gini Index: **0.36**
- For <ins><b>money</ins></b> - Gini Index: **0.486**

### $\large {\color{Purple}\underline{\textrm{Drawing the root}}}$ 



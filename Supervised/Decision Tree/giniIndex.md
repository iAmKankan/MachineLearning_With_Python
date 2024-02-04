
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

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/dc536428-1399-4383-8fef-8c4c5156c09a" width=40%/>
  <br>
  <ins><b><i></i></b></ins>
</p>

$$\Large {\color{purple}Gini (S) = 1 - \[(5/5) ^ 2\] = 0}$$

* For $\large{\color{purple}parents = no}$ , there are **2** examples with $\large{\color{purple}decision = tennis}$, **1** example with $\large{\color{purple}decision = stay\\_in}$, **1** example with $\large{\color{purple}decision = shopping}$ and **1** example with $\large{\color{purple}decision = movie}$.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/96b01b21-fa03-4f06-bea7-4c90880d6f1d" width=40%/>
  <br>
  <ins><b><i></i></b></ins>
</p>

$$\Large {\color{purple}Gini (S) = 1 - \[(2/5) ^ 2 + (1/5) ^ 2 + (1/5) ^ 2 + (1/5) ^ 2\] = 0.72}$$

$$\Large {\color{purple}Weighted\ Average(Parents) = 0*( 5 10 )+ \[ 0.72(5/10) = 0.36 \]}$$

###  ♠️ $\large{\color{Purple}weather \rightarrow \\{sunny, rainy, windy \\} }$
Attribute <ins><b>weather</b></ins> has 3 possible values of **3 instances of 'sunny'**, **3 instances of 'rainy'** and **4 instances of 'windy'**.
* For $\large{\color{purple}weather = sunny}$ , there are **2** examples with $\large{\color{purple}decision = movie}$ and **1** with $\large{\color{purple}decision = tennis}$.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/ed8ddcdc-fea9-4a63-a4ae-8e52b9d01d9e" width=40%/>
  <br>
  <ins><b><i></i></b></ins>
</p>

$$\Large {\color{purple} Gini(Sunny)= 1 - \[(2/3) ^ 2 + (1/3) ^ 2\] = 0.44}$$

* For $\large{\color{purple}weather = rainy}$, there are **2** examples with $\large{\color{purple}decision = movie}$ and **1** example with $\large{\color{purple}decision = stay\\_in}$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/1cd69e54-36c0-4198-b983-83278d69febc" width=40%/>
  <br>
  <ins><b><i></i></b></ins>
</p>

$$\Large {\color{purple}Gini(Rainy)= 1 - \[(2/3) ^ 2 + (1/3) ^ 2\] = 0.44 }$$

* For $\large{\color{purple}weather = windy}$ , there are **3** examples with $\large{\color{purple}decision = movie}$ and **1** example with $\large{\color{purple}decision = shopping}$

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/8486a056-c7cb-4ba1-8242-0ed1365dafe2" width=40%/>
  <br>
  <ins><b><i></i></b></ins>
</p>

$$\Large {\color{purple}Gini(Windy)= 1 - \[(3/4) ^ 2 + (1/4) ^ 2\] = 0.375}$$

$$\Large {\color{purple} Weighted\ Average(Weather) = 0.444(3/10) + 0.444(3/10) + 0.375(4/10) = 0.416}$$

### $\large {\color{Purple}\underline{\textrm{Final Gini-Index of }} Step 1 \\# }$ 

- For <ins><b>weather</ins></b> - Gini Index: **0.416**
- For <ins><b>parents</ins></b> - Gini Index: **0.36**
- For <ins><b>money</ins></b> - Gini Index: **0.486**

### $\large {\color{Purple}\underline{\textrm{Drawing the root}}}$ 

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/eb031cb6-5d8a-4f32-9f0d-0c3f7370af25" width=50%/>
  <br>
  <ins><b><i>The root</i></b></ins>
</p>

* As we can clearly see the **Gini Index** of the attribute $\large{\color{purple}parent}$ is the lowest, therefore we have no problem to make parent as **root node**.
* As $\large{\color{purple}parent = yes}$ having <ins><b>only one kind of  instances</ins></b> where $\large{\color{purple}decision = movie}$ then we can clearly say that this is the **leaf node**.

### $\large {\color{Purple}\underline{\textrm{Final Tree after }} Step 1 \\# }$ 

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/6b5a6979-7875-492f-bc4e-d1f0441d1af9" width=80%/>
  <br>
  <ins><b><i>The tree after the first step</i></b></ins>
</p>

  
### $\large {\color{Purple}Step 2 \\# }$ 
#### Compute the <ins>Gini Index</ins> on the leftover data.

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/df23d2ad-6f51-4156-9ca9-03bd05963347" width=70%/>
  <br>
  <ins><b><i>Gini-Index step 2</i></b></ins>
</p>

###  ♠️ $\large{\color{Purple}\underline{parents = no} \Rightarrow \underline{weather = \\{ sunny, rainy, windy \\} }}$

### $\large{\color{purple}\underline{weather =  sunny}:}$
* For  $\large{\color{purple}parent=no}$ |  $\large{\color{purple}weather = sunny}$ , there are **2 examples** with  $\large{\color{purple}tennis}$

$$\Large {\color{purple}Gini(sunny)= 1 - \[(2/2) ^ 2 \] = 0}$$

### $\large{\color{purple}\underline{weather =  rainy}:}$
* For  $\large{\color{purple}parent=no}$ |  $\large{\color{purple}weather = rainy}$ , there is **1 example** with  $\large{\color{purple}stay\\_in}$

$$\Large {\color{purple}Gini(rainy)= 1 - \[(1/1) ^ 2 \] = 0}$$

### $\large{\color{purple}\underline{weather =  windy}:}$
* For  $\large{\color{purple}parent=no}$ |  $\large{\color{purple}weather = windy}$ , there is **1 example** with  $\large{\color{purple}movie}$, **1 example** with  $\large{\color{purple}shopping}$

$$\Large {\color{purple}Gini(windy)= 1 - \[(1/1) ^ 2 + (1/1) ^ 2 \] = 0.5}$$

$$\Large {\color{purple} Weighted\ Average(parent=no | weather) = 0 * (2/5)+ 0 * (1/5)+ 0.5 * (2/5) = 0.2 }$$

###  ♠️ $\large{\color{Purple}\underline{parents = no} \Rightarrow \underline{money = \\{rich, poor \\} }}$
### $\large{\color{purple}\underline{money =  rich}:}$
* For  $\large{\color{purple}parent=no}$ |  $\large{\color{purple}money = rich}$ , there is **1 example** with  $\large{\color{purple}stay\\_in}$, **1 example** with  $\large{\color{purple}shopping}$ and  **2 examples** with  $\large{\color{purple}tennis}$

$$\Large {\color{purple} Gini(rich) = 1 - \[(1/4) ^ 2 + (1/4) ^ 2 + (2/4) ^ 2 \] = 0.625}$$

### $\large{\color{purple}\underline{money =  poor}:}$

* For  $\large{\color{purple}parent=no}$ |  $\large{\color{purple}money = poor}$ , there is **1 example** with  $\large{\color{purple}movie}$ .

$$\Large {\color{purple} Gini(poor) = 1 - \[(1/1) ^ 2 \] = 0}$$

$$\Large {\color{purple} Weighted\ Average(parent=no | money) = 0.625 * (4/5)+ 0 * (1/5)= 0.5 }$$


### $\large {\color{Purple}\underline{\textrm{Final Gini-Index of }} Step 2 \\# }$ 

- For <ins><b>parent=no | weather</ins></b> - Gini Index: **0.2**
- For <ins><b>parent=no | money</ins></b> - Gini Index: **0.5**

### $\large {\color{Purple}\underline{\textrm{Drawing the Tree}}}$ 

<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/eb031cb6-5d8a-4f32-9f0d-0c3f7370af25" width=50%/>
  <br>
  <ins><b><i>The root</i></b></ins>
</p>

* As we can clearly see the **Gini Index** of the attribute $\large{\color{purple}parent=no | weather}$ is the lowest, therefore we have no problem to make parent as a **parent node**.
* As $\large{\color{purple}parent = no| weather}$ having <ins><b>only one kind of  instances</ins></b> where $\large{\color{purple} weather = sunny}$  where $\large{\color{purple}decision = tennis }$ then we can clearly say that this is the **leaf node**.
* As $\large{\color{purple}parent = no| weather}$ having <ins><b>only one kind of  instances</ins></b> where $\large{\color{purple} weather = rainy}$  where $\large{\color{purple}decision = stay\\_in }$ then we can clearly say that this is the **leaf node**.
* As $\large{\color{purple}parent = no| weather}$ having <ins><b>only thow different kind ofs  instances</ins></b> where $\large{\color{purple} weather = sunny}$  where $\large{\color{purple}decision = movie }$ and $\large{\color{purple}decision = shopping }$ then we can clearly need to go further.

  

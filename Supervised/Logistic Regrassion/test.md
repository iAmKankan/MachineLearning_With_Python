#### ♠️ The output of Sigmoid function is -

$$\Large{\color{purple} \mathrm{\hat{y}^{(i)} = \sigma (w^\top x^{(i)} +b)} \cdots \cdots \cdots , \ \ where \mathrm{ \ \ \ \ \sigma(z^{(i)}) = \dfrac{1}{1+e^{-z^{(i)}}}}} $$

♠️ Given $\large{\color{purple} \\{ (x^{(1)},y^{(1)}) \cdots (x^{(m)},y^{(m)}) \\} }$ and we want $\large{\color{purple}\  \hat{y}^{(i)} \approx y^{(i)} }$  \[ <ins> The superscript <b>i</b> refers to the <b>i<sup>th</sup></b> training example</ins> \]

### 🔲 <ins>Least Squared Error:</ins>

$$\Large{\color{Purple} {J^{\normalsize{LS}} = \frac{1}{2} (y- \hat{y})^2}}$$

### Why Least-Squared cost function BAD for Logistic regression?
$\large Answer:$ What we do for **Linear Regression**  we take the sum of all these examples and take an average. But it is not a good cost function for Binary classification. There are several reasons 

### $\large{\color{Purple}\underline{Reason \ 1 \\#}}$
Suppose the cost that you incur for misclassification, $\large{\color{Purple}y}$ is class $\large{\color{Purple}0}$ and $\large{\color{Purple}\hat{y}}$ is as $\large{\color{Purple}1}$ or very close like $\large{\color{Purple}0.99}$

The cost that you incur for misclassification, that is when $\large{\color{Purple}y}$ is **0** if you say $\large{\color{Purple}\hat{y}}$ is **1** or close to **1** let us say **0.99**, so when we want to predict something as clear as classification and you give a misclassification, the cost incurred for that is actually very low, that is we do not penalize this cost high enough, even though there is a penalty it is not high enough. So because of that, this is one of the reasons why the usual least square cost function is a bad cost function for classification.

### $\large{\color{Purple}\underline{Reason \ 2 \\#}}$
For **Logistic Regression** we don't use the same **loss function** as for **Linear Regression** because when we come to learn the parameters of **optimization** problem, it become **non-convex**, which will cause multiple **Local Optima** and the **Gradient Descent** may not find the **Global Optima**. 

<p align="center">
<img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/7b238c0e-d650-497b-884a-ae4fa70a1944" width=40%/>
  <br><ins><b><i> Convex vs Non-Convex </i></b></ins>
</p>

### 🔲 <ins> Binary Cross Entropy</ins>
$$ {\color{Purple} \Huge \boxed{\mathbf{ J= - \Bigl\\{ y \ln\hat{y} + (1-y) \ln(1-\hat{y}) \Bigl\\} }} }$$

### ♠️ Desirable properties for classification cost function-
1. $\large{\color{Purple} \mathbf{J = 0} \textit{, if } \mathbf{y=\hat{y}} }$
2. $\large{\color{Purple} \mathbf{J} \textrm{ should be very high for }\mathbf{missclassification}}$
3. $\large{\color{Purple} \mathbf{J \geq 0}}\textrm{    [required for consistency]}$

### $\large{\color{purple} Case \\# 1}$
1. $\large {\color{Purple}y=0}$ and $\large {\color{Purple}\hat{y}=0}$  $\large {\color{Purple}( \hat{y} \approx 0)}$ $\large {\color{Purple}\Rightarrow J \approx 0}$

### $\large{\color{purple} Case \\# 2}$

1. $\large {\color{Purple}y=1}$ and $\large {\color{Purple}\hat{y} \approx 1}$  $\large {\color{Purple}\Rightarrow J \approx 0}$




* So, $\large{\color{Purple} y}$ is either a **0** or **1**, $\large{\color{Purple} \hat{y}}$ is between **0** and **1**. 
* Therefore $\large{\color{Purple} \ln \hat{y}}$ is going to be **negative (-ve)** . 
* $\large{\color{Purple} y}$ is going to be either **0** or **1**, 
* So this whole term Therefore $\large{\color{Purple} y \ln \hat{y}}$ is **negative (-ve)**. 
* Similarly this term Therefore $\large{\color{Purple} (1 − y ) \ln(1− \hat{y})}$  is also **negative (-ve)**, and that is why we have minus sign so that the whole term actually becomes positive. So that it is consistent with least squares.


#### 1. For $\large{\color{Purple} \mathbf{J = 0} \textit{, if } \mathbf{y=\hat{y}} }$ and for  $\large{\color{Purple} \mathbf{J \geq 0}}$
#### Example
* Suppose $\large \mathrm{y=0, \ \  \hat{y}=0} \textrm{ or close to 0, } \mathbf{ J \approx 0} $
* Suppose $\large \mathrm{y=1, \ \  \hat{y} \approx 1} ,  \mathbf{ J \approx 0} $
* Suppose $\large \mathrm{y=0, \ \  \hat{y} \approx 1} ,  \mathbf{ J \to \infty} $

#### 2. For $\large{\color{Purple} \mathbf{J} \textrm{ would be very high for }\mathbf{missclassification}}$
##### The equation

$$ {\color{Purple} \large \mathbf{ J= - \Bigl\\{ y \ln\hat{y} + (1-y) \ln(1-\hat{y}) \Bigl\\} }}$$



* $\large{\color{Purple} y=0,} \textrm{ makes this term } {\color{Purple}(y \ln\hat{y}) = 0 } $ 
* $\large{\color{Purple} y=0,} \textrm{ makes this term } {\color{Purple}((1-y)) \approx 0 } \textrm{ and } {\color{Purple} \hat{y} \approx 0,} \textrm{ makes this term } {\color{Purple}((1-\hat{y})) \approx 0 } $
* So, $\large{\color{Purple} \ln 0 = - \infty } $ 
* $\large{\color{Purple} y=0, \hat{y} \approx 1 \Rightarrow  \mathbf{J} \to \infty } \textrm{, Hence proved } $
* $\large{\color{Purple} y=1, \hat{y} \approx 0 \Rightarrow  \mathbf{J} \to \infty } \textrm{, Hence proved } $

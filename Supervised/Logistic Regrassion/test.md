#### ♠️ The output of Sigmoid function is -

$$\Large{\color{purple} \mathrm{\hat{y}^{(i)} = \sigma (w^\top x^{(i)} +b)} \cdots \cdots \cdots , \ \ where \mathrm{ \ \ \ \ \sigma(z^{(i)}) = \dfrac{1}{1+e^{-z^{(i)}}}}} $$

♠️ Given $\large{\color{purple} \\{ (x^{(1)},y^{(1)}) \cdots (x^{(m)},y^{(m)}) \\} }$ and we want $\large{\color{purple}\  \hat{y}^{(i)} \approx y^{(i)} }$  \[ <ins> The superscript <b>i</b> refers to the <b>i<sup>th</sup></b> training example</ins> \]

### 🔲 <ins>Least Squared Error:</ins>

$$\Large{\color{Purple} {J^{\normalsize{LS}} = \frac{1}{2} (y- \hat{y})^2}}$$

### Why Least-Squared cost function BAD for Logistic regression?
What we do for **Linear Regression**  we take the sum of all these examples and take an average. But it is not a good cost function for Binary classification. There are several reasons 

### $\large{\color{Purple}\underline{Reason \ 1 \\#}}$
Suppose the cost that you incur for misclassification, $\large{\color{Purple}y}$ is class $\large{\color{Purple}0}$ and $\large{\color{Purple}\hat{y}}$ is as $\large{\color{Purple}1}$ or very close like $\large{\color{Purple}0.99}$

The cost that you incur for misclassification, that is when $\large{\color{Purple}y}$ is **0** if you say $\large{\color{Purple}\hat{y}}$ is **1** or close to **1** let us say **0.99**, so when we want to predict something as clear as classification and you give a misclassification, the cost incurred for that is actually very low, that is we do not penalize this cost high enough, even though there is a penalty it is not high enough. So because of that, this is one of the reasons why the usual least square cost function is a bad cost function for classification.

### $\large{\color{Purple}\underline{Reason \ 2 \\#}}$
For **Logistic Regression** we don't use the same **loss function** as for **Linear Regression** because when we come to learn the parameters of **optimization** problem, it become **non-convex**, which will cause multiple **Local Optima** and the **Gradient Descent** may not find the **Global Optima**. 

<p align="center">
<img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/7b238c0e-d650-497b-884a-ae4fa70a1944" width=40%/>
  <br><ins><b><i> Convex vs Non-Convex </i></b></ins>
</p>


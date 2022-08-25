## Index
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

<p align="center" ><img src="https://user-images.githubusercontent.com/12748752/186566132-7e8711f4-21ba-41dc-870f-d350c8916830.png" width=40%/>
<br><ins><b>Sinusoidal Curve</b></ins></p>

This green curve is a **Sinusoidal Curve**, from which we draw the followings-
* Some **data points** at some specific intervals, 
* And we just add some **noise** to this dataset which is given by the **blue dot** or **blue circles**.

So the idea here is, we want to fit into a polynomial and to vary the degree of the polynomial and see how the fix look like. We fit them by using an error term to perform the regression with **least squared error**

$$\large{\color{Purple} \sum_{i=1}^{m} \Bigl(y^{(i)}- \hat{y}^{(i)} \Bigl)^2}$$ 

$$\large or$$

$$\large{\color{Purple} \sum_{i=1}^{m} \Bigl( t^{(i)} -y(x^{(i)};w) \Bigl)^2}$$

So **_t_** is the ground truth or the correct answer and whatever your polynomial outputs, and it is given by **_y_**, so your error is basically what you are going to use,



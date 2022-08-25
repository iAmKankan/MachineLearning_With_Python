## Index
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)

### The Curve 

<p align="center" ><img src="https://user-images.githubusercontent.com/12748752/186566132-7e8711f4-21ba-41dc-870f-d350c8916830.png" width=30%/>
<br><ins><b>Sinusoidal Curve</b></ins></p>

This green curve is a **Sinusoidal Curve**, from which we draw the followings-
* Some **data points** at some specific intervals, 
* And we just add some **noise** to this dataset which is given by the **blue dot** or **blue circles**.

### Fitting
<p align="center"> <img src="https://user-images.githubusercontent.com/12748752/186587311-d3080729-7d9a-4882-9d9b-88e6aac49cab.png" width=30% />
<br><ins><b>Sum-of-squares Error Function</b></ins></p>


So the idea here is, we want to fit into a polynomial and to vary the degree of the polynomial and see how the fix look like. We fit them by using an error term to perform the regression with **least squared error**

$$\large{\color{Purple} \sum_{i=1}^{m} \Bigl(y^{(i)}- \hat{y}^{(i)} \Bigl)^2}$$ 

$$\large or$$

$$\large{\color{Purple} \sum_{i=1}^{m} \Bigl( t^{(i)} -y(x^{(i)};w) \Bigl)^2}$$

So **_t_** is the ground truth or the correct answer and whatever your polynomial outputs, and it is given by **_y_**, so your error is basically what you are going to use,

### 0<sup>th</sup> Order, 1<sup>st</sup>Order & 3<sup>rd</sup> Order Polynomials

<img src="https://user-images.githubusercontent.com/12748752/186598693-db686c38-6e19-4cf5-82ca-efef4a1e2fe2.png" />

So, at the extreme left we have a **zero degree polynomial**, which is nothing but a **constant term**, so as you can see there is a red line, which is actually the fit, the fitted curve, of course does not match the data that we have used.

At the middle we use a **first degree polynomial**, which is nothing but a **linear fit**, and did not fit

At the right we have **third degree polynomial**. 


### 9<sup>th</sup> Order Polynomials
<p align="center"> <img src="https://user-images.githubusercontent.com/12748752/186589809-16614600-9242-48a5-9841-900db3964731.png" width=30% />
<br><ins><b>9<sup>th</sup> Order Polynomials</b></ins></p>


 
So ideally when you are done with the fit, you would expect the **red curve** to _lie close_ to the **green curve**, but in this case, _in between samples is actually off_. 

So even the with higher degree polynomial is, we are able to fit every point exactly, so that our **fitting error is very small**. We see that in points, other than the blue circles, it is actually **quite far from the ground truth**.

## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

## The Idea
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
* Gradient Descent is a _`generic optimization algorithm`_ capable of finding optimal solutions to a wide range of problems. 
* The general idea of _**Gradient Descent**_ is to tweak parameters iteratively in order to minimize a _cost function_. 

> ### Example 01
* _Suppose you are lost in the mountains in a dense fog, and you can only feel the slope of the ground below your feet_. 
* _A good strategy to get to the bottom of the valley quickly is to go downhill in the direction of the steepest slope_. 
* This is exactly what Gradient Descent does: it measures the local gradient of the error function with regard to the _`parameter vector`_ **_θ_**, and it goes in the direction of descending gradient. 
* Once the gradient is zero, you have reached a minimum!

> ### Steps
* **First**, start by filling **_θ_** with random values (this is called _`random initialization`_). 
* **Then** you improve it gradually, taking one baby step at a time, each step attempting to decrease the cost function (e.g., the MSE), until the algorithm converges to a minimum.

<img src="https://user-images.githubusercontent.com/12748752/146699335-d3b9e07e-1fe4-43d0-a805-14481610dc7e.png" width=40%/>

> In this depiction of Gradient Descent, the model parameters are initialized randomly and get tweaked repeatedly to minimize the cost function; the learning step size is proportional to the slope of the cost function, so the steps gradually get smaller as the parameters approach the minimum

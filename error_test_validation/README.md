![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

## Testing and Validating 

<img src="https://user-images.githubusercontent.com/12748752/141670977-ae3e17a8-0636-4fb6-a052-cf4de904f5a9.png" >

* The only way to know how well a model will generalize to new cases is to actually try it out on new cases. 
* One way to do that is to put your model in production and monitor how well it performs. 
* This works well, but if your model is horribly bad, your users will complain—not the best idea. 
* A better option is to split your data into two sets: the **training** set and the **test set**. 
* As these names imply, you train your model using the training set, and you test it using the test set. The error rate on new cases is called the generalization error (or out-of-sample error), and by evaluating your model on the test set, you get an estimate of this error. This value tells you how well your model will perform on instances it has never seen before. If the training error is low (i.e., your model makes few mistakes on the training set) but the generalization error is high, it means that your model is overfitting the training data.

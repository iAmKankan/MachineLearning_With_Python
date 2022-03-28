## Index
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

### Training Sets, Validation Sets, and Holdout Sets

### Partitioning Data
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
The first step in developing a machine learning model is training and validation. In order to train and validate a model, you must first partition your dataset, which involves choosing what percentage of your data to use for the training, validation, and holdout sets. The following example shows a dataset with 64% training data, 16% validation data, and 20% holdout data.

### What is a Training Set?
A training set is the subsection of a dataset from which the machine learning algorithm uncovers, or “learns,” relationships between the features and the target variable. In supervised machine learning, training data is labeled with known outcomes.

### What is a Validation Set?
A validation set is another subset of the input data to which we apply the machine learning algorithm to see how accurately it identifies relationships between the known outcomes for the target variable and the dataset’s other features.

### What is a Holdout Set?
Sometimes referred to as “testing” data, a holdout subset provides a final estimate of the machine learning model’s performance after it has been trained and validated. Holdout sets should never be used to make decisions about which algorithms to use or for improving or tuning algorithms.


* A typical regression task is to predict a **_target_** numeric value, such as the price of a car, given a set of **_features_** (mileage, age, brand, etc.) called **_predictors_**.

* In Machine Learning an attribute is a data type (e.g., “mileage”), while a feature has several meanings, depending on the context, but generally means an attribute plus itsvalue (e.g., “mileage = 15,000”). Many people use the words attribute and feature interchangeably.

## Testing and Validating 

<img src="https://user-images.githubusercontent.com/12748752/141670977-ae3e17a8-0636-4fb6-a052-cf4de904f5a9.png" >

* The only way to know how well a model will generalize to new cases is to actually try it out on new cases. One way to do that is to put the model in production and monitor how well it performs. 
* This works well, but if your model is horribly bad, your users will complain—not the best idea. 
* A better option is to split your data into two sets: the **_training_** set and the **_test set_**. 
* As these names imply, you train your model using the training set, and you test it using the test set. The error rate on new cases is called the generalization error (or out-of-sample error), and by evaluating your model on the test set, you get an estimate of this error. This value tells you how well your model will perform on instances it has never seen before. If the training error is low (i.e., your model makes few mistakes on the training set) but the generalization error is high, it means that your model is overfitting the training data.

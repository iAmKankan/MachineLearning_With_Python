# K-nearest-neighbor
## Definition
* It can be used for both classification and regression.
* Stores all the classes and classifies new classes based on a similarity measure.
* The 'K' is KNN algorithm is the nearest neighbours we wish to take a vote from.
* Also called an instance-based or memory-based learning
* Lazy Algorithm
    - K-NN is a lazy learner because Because it does not create a generalized model during the time of training, so the testing phase is very important where it does the actual job. 
    - Hence Testing is very costly - in terms of time & money.
    - For example, the logistic regression algorithm learns its model weights (parameters) during training time. In contrast, there is no training time in K-NN.
    - This property doesn’t come without a cost: The “prediction” step in K-NN is relatively expensive!
        
         - Each time we want to make a prediction, K-NN is searching for the nearest neighbor(s) in the entire training set! 
         - There are certain tricks such as **BallTrees** and **KDtrees** to speed this up a bit.)
    - To summarize: An eager learner has a model fitting or training step. A lazy learner does not have a training phase.
    
* Only we have to find the stable value of K
     - K to your chosen number of neighbors

* Problemetic for large datasets
    - KNN captures the idea of similarity (sometimes called distance, proximity, or closeness) with some mathematics.
    
* The result of current neughborhood every time.
* odd numbers of K (not getting the tie 
* K= the number of dots you need to consider.
* **Not working in High dimentional data.**

* Distance is measured by -
    * For continuous variables.
        * Eucladian Distance 
        * Manhattan Distance
        * Minkowski Distance
    * For categorical variables.
        * Hamming Distance






<img src="knn.png?raw=true">


A k-nearest-neighbor algorithm, often abbreviated k-nn, is an approach to data classification that estimates how likely a data point is to be a member of one group or the other depending on what group the data points nearest to it are in.

## Methods of calculating distance between points:
### Algorithm		
A case is classified by a majority vote of its neighbors, with the case being assigned to the class most common amongst its K nearest neighbors measured by a distance function. If K = 1, then the case is simply assigned to the class of its nearest neighbor.    
<img src="KNN_similarity.png?raw=true">

<img src="KNN_hamming.png?raw=true">

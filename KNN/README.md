# K-nearest-neighbor
## Definition
* Stores all the classes and classifies new classes based on a similarity measure.
* The 'K' is KNN algorithm is the nearest neighbours we wish to take a vote from.

<img src="knn.png?raw=true">


A k-nearest-neighbor algorithm, often abbreviated k-nn, is an approach to data classification that estimates how likely a data point is to be a member of one group or the other depending on what group the data points nearest to it are in.

## Methods of calculating distance between points:
### Algorithm		
A case is classified by a majority vote of its neighbors, with the case being assigned to the class most common amongst its K nearest neighbors measured by a distance function. If K = 1, then the case is simply assigned to the class of its nearest neighbor. 
<img src="KNN_similarity.png?raw=true">

<img src="KNN_hamming.png?raw=true">

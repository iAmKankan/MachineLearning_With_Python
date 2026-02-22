## Index
![dark](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
![light](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)

### K-means Clustering
### What is Clustering?
$\large{\color{Purple}\text{Answer:}}$ Clustering is an **unsupervised machine learning technique** that automatically groups **unlabeled data points** based on similarity. Grouping items with similar characteristics helps identify natural, hidden patterns within datasets. Common applications include **market segmentation**, **image segmentation**, **anomaly detection**, and **data compression**.
* **Goal**: Discover the **natural grouping** or structure in unlabeled data without predefined categories.
* **How**: Data points are assigned to clusters based on similarity or distance measures.
* **Similarity Measures**: Can include Euclidean distance, cosine similarity or other metrics depending on data type and clustering method.
* **Output**: Each group is assigned a cluster ID, representing shared characteristics within the cluster.
### Core Concepts of Clustering
* **Unsupervised Learning**: No predefined tags or labels are used; the algorithm finds structure independently.
* **Similarity Metrics**: Data points are grouped based on proximity using metrics like Euclidean distance or cosine similarity.
* **Intra-cluster Similarity**: Objects in the same cluster are more similar to each other than to those in other clusters.
### What is K-Means Clustering?
$\large{\color{Purple}\text{Answer:}}$ **K-Means Clustering** groups similar data points into clusters without needing labeled data. It is used to uncover hidden patterns when the goal is to organize data based on similarity.

* Helps identify natural groupings in unlabeled datasets
* Works by grouping points based on distance to cluster centers
* Commonly used in customer segmentation, image compression, and pattern discovery
* Useful when you need structure from raw, unorganized data

### Working of K-Means Clustering
* K-means clustering measures similarity using ordinary straight-line distance (**Euclidean** distance, in other words).
* It creates clusters by placing a number of points, called centroids, inside the feature-space.
* Each point in the dataset is assigned to the cluster of whichever centroid it's closest to.
* The "k" in "k-means" is how many **centroids** (that is, **clusters**) it creates. You define the **k** yourself.

**Voronoi tessellation**: You could imagine each centroid capturing points through a sequence of radiating circles. When sets of circles from competing centroids overlap, they form a line. The result is what's called a **Voronoi tessellation**. The tessellation shows you to which clusters future data will be assigned; the tessellation is essentially what **k-means** learns from its training data.

The clustering on the [Ames](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data) dataset above is a k-means clustering. Here is the same figure with the **tessellation** and centroids shown.

<p align="center">
  <img width=20% src="https://github.com/user-attachments/assets/005c7932-1568-4790-ad15-0602c4bc3f7a" />
  <br><ins><b><i>K-means clustering creates a Voronoi tessellation of the feature space</i></b></ins>
</p>

Let's review how the k-means algorithm learns the clusters and what that means for feature engineering. We'll focus on three parameters from scikit-learn's implementation:` n_clusters`, `max_iter`, and `n_init`.

It's a simple two-step process. The algorithm starts by randomly initializing some predefined number (n_clusters) of centroids. It then iterates over these two operations:

assign points to the nearest cluster centroid
move each centroid to minimize the distance to its points
It iterates over these two steps until the centroids aren't moving anymore, or until some maximum number of iterations has passed (max_iter).

It often happens that the initial random position of the centroids ends in a poor clustering. For this reason the algorithm repeats a number of times (n_init) and returns the clustering that has the least total distance between each point and its centroid, the optimal clustering.

The animation below shows the algorithm in action. It illustrates the dependence of the result on the initial centroids and the importance of iterating until convergence.

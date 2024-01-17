
### $\Large{\color{Purple}\textbf{Index}}$
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
   * Clustering
      * K-Means
      * DBSCAN
      * Hierarchical Cluster Analysis (HCA)
   * Anomaly detection and novelty detection
      * One-class SVM
      * Isolation Forest
  * [Visualization and dimensionality reduction](https://github.com/iAmKankan/Data-Gathering-And-Preprocessing/tree/main/Dimensionality_Reduction#readme)
     * [Principal Component Analysis (PCA)](https://github.com/iAmKankan/Data-Gathering-And-Preprocessing/blob/main/Dimensionality_Reduction/PCA.md)
     * Kernel PCA
     * Locally-Linear Embedding (LLE)
     * t-distributed Stochastic Neighbor Embedding (t-SNE)
  * Association rule learning
     * Apriori
     * Eclat

![plum](https://user-images.githubusercontent.com/12748752/126882596-b9ba4645-7001-435e-9a3c-d4416a2543c1.png)
###  ⬛ $\Large{\color{Blue}\mathcal{Unsupervised\ Machine\ Learning}}$
### ♠️ <ins>What is Unsupervised Machine Learning</ins>? 
$\Large Answer:$ Unsupervised learning, also known as unsupervised machine learning, uses machine learning algorithms to analyze and cluster unlabeled datasets. These algorithms discover hidden patterns or data groupings without the need for human intervention.
Its ability to discover similarities and differences in information make it the ideal solution for exploratory data analysis, cross-selling strategies, customer segmentation, and image recognition.

### ♠️ <ins>How does unsupervised learning work</ins>? 
$\Large Answer:$  Unsupervised learning works by analyzing unlabeled data to identify patterns and relationships. The data is not labeled with any predefined categories or outcomes, so the algorithm must find these patterns and relationships on its own. This can be a challenging task, but it can also be very rewarding, as it can reveal insights into the data that would not be apparent from a labeled dataset.

The input to the unsupervised learning models is as follows: 

* $\large{\color{Purple}\textrm{Unstructured data:}}$ May contain noisy(meaningless) data, missing values, or unknown data. Example: Digital photos, audio, and video files
* $\large{\color{Purple}\textrm{Unlabeled data:}}$ Data only contains a value for input parameters(features), there is no targeted value(lebel or output or Y). It is easy to collect as compared to the labeled one in the Supervised approach.

### Unsupervised Learning Algorithm Types
There are mainly 3 types of Algorithms which are used for Unsupervised dataset.
* $\large{\color{Purple}\textrm{Clustering}}$
* $\large{\color{Purple}\textrm{Association Rule Learning}}$
* $\large{\color{Purple}\textrm{Dimensionality Reduction}}$
* $\large{\color{Purple}\textrm{Anomaly detection and novelty detection}}$


### 🔲 $\large{\color{Purple}\underline{\textrm{Clustering}}}$
Clustering in unsupervised machine learning is the process of grouping unlabeled data into clusters based on their similarities. The goal of clustering is to identify patterns and relationships in the data without any prior knowledge of the data’s meaning.

Broadly this technique is applied to group data based on different patterns, such as similarities or differences, our machine model finds. These algorithms are used to process raw, unclassified data objects into groups. 

Some common clustering algorithms

* <ins><b>K-means Clustering:</b></ins> Partitioning Data into K Clusters
* <ins><b>Hierarchical Clustering:</b></ins> Building a Hierarchical Structure of Clusters
* <ins><b>Density-Based Clustering (DBSCAN):</b></ins> Identifying Clusters Based on Density
* <ins><b>Mean-Shift Clustering:</b></ins> Finding Clusters Based on Mode Seeking
* <ins><b>Spectral Clustering:</b></ins> Utilizing Spectral Graph Theory for Clustering

### 🔲 $\large{\color{Purple}\underline{\textrm{Association Rule Learning}}}$
Association rule learning is also known as association rule mining is a common technique used to discover associations in unsupervised machine learning. This technique is a rule-based ML technique that finds out some very useful relations between parameters of a large data set. This technique is basically used for market basket analysis that helps to better understand the relationship between different products. For e.g. shopping stores use algorithms based on this technique to find out the relationship between the sale of one product w.r.t to another’s sales based on customer behavior. Like if a customer buys milk, then he may also buy bread, eggs, or butter. Once trained well, such models can be used to increase their sales by planning different offers.

* <ins><b>Apriori Algorithm:</b></ins> A Classic Method for Rule Induction
* <ins><b>FP-Growth Algorithm:</b></ins> An Efficient Alternative to Apriori
* <ins><b>Eclat Algorithm:</b></ins> Exploiting Closed Itemsets for Efficient Rule Mining
* <ins><b>Efficient Tree-based Algorithms:</b></ins> Handling Large Datasets with Scalability
  
### 🔲 $\large{\color{Purple}\underline{\textrm{Dimensionality Reduction}}}$
Dimensionality reduction is the process of reducing the number of features in a dataset while preserving as much information as possible. This technique is useful for improving the performance of machine learning algorithms and for data visualization. Examples of dimensionality reduction algorithms includeDimensionality reduction is the process of reducing the number of features in a dataset while preserving as much information as possible.

* <ins><b>Principal Component Analysis (PCA):</b></ins> Linear Transformation for Reduced Dimensions
* <ins><b>Linear Discriminant Analysis (LDA):</b></ins> Dimensionality Reduction for Discrimination
* <ins><b>Non-negative Matrix Factorization (NMF):</b></ins> Decomposing Data into Non-negative Components
* <ins><b>Locally Linear Embedding (LLE):</b></ins> Preserving Local Geometry in Reduced Dimensions
* <ins><b>Isomap: Capturing Global Relationships in Reduced Dimensions</b></ins>

### 🔲 $\large{\color{Purple}\underline{\textrm{Anomaly detection and novelty detection}}}$


### 🔲 $\large{\color{Purple}\underline{\textrm{Applications of Unsupervised Machine Learning}}}$

Machine learning techniques have become a common method to improve a product user experience and to test systems for quality assurance. Unsupervised learning provides an exploratory path to view data, allowing businesses to identify patterns in large volumes of data more quickly when compared to manual observation. Some of the most common real-world applications of unsupervised learning are:

* **News Sections:** Google News uses unsupervised learning to categorize articles on the same story from various online news outlets. For example, the results of a presidential election could be categorized under their label for “US” news.
* **Computer vision:** Unsupervised learning algorithms are used for visual perception tasks, such as object recognition.  
* **Medical imaging:** Unsupervised machine learning provides essential features to medical imaging devices, such as image detection, classification and segmentation, used in radiology and pathology to diagnose patients quickly and accurately.
* **Anomaly detection:** Unsupervised learning models can comb through large amounts of data and discover atypical data points within a dataset. These anomalies can raise awareness around faulty equipment, human error, or breaches in security.
* **Customer personas:** Defining customer personas makes it easier to understand common traits and business clients' purchasing habits. Unsupervised learning allows businesses to build better buyer persona profiles, enabling organizations to align their product messaging more appropriately.
* **Recommendation Engines:** Using past purchase behavior data, unsupervised learning can help to discover data trends that can be used to develop more effective cross-selling strategies. This is used to make relevant add-on recommendations to customers during the checkout process for online retailers.


### References:
![grape](https://user-images.githubusercontent.com/12748752/126882595-d1f5449e-14bb-4ab3-809c-292caf0858a1.png)
* [IBM](https://www.ibm.com/topics/unsupervised-learning)
* [Geeks for geeks](https://www.geeksforgeeks.org/ml-types-learning-part-2/?ref=header_search)

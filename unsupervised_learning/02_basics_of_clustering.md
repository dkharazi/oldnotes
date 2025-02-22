## Motivating Categorization
- Dividing data into discrete categories is one of the most common kinds of data mining task
- Often these categories are things which are given to us in advance (i.e. based on historical data)
- Some examples of categories that could be given to us:
	- Cells: cancerous or not
	- Credit applicant: pay back loan or not
	- Text: political or religious
	- Picture: flower, tiger, or ocean
- There are two basic forms of categorization:
	1. Classification
	2. Clustering
- Classification is the process of assigning new data to pre-existing categories
	- These categories are also referred to as classes
	- The goal of classification methods is to accurately assign new, unlabeled examples from the test data to these pre-determined classes
	- This process is an example of supervised learning
- Clustering is the process of discovering new categories for our data
	- These categories are also referred to as clusters
	- This process is an example of unsupervised learning

## Clustering Use-Cases
1. Testing classes against objective, deterministic features if the classes were generated from an biased (or subjective) source
	- Even if our data comes to us with class labels attached, it’s often wise to be skeptical of their use
	- Official classification schemes are often the end result of a mix of the following:
		- Practical experience
		- Intuition
		- Theory
		- Prejudice
		- Ideas copied from somewhere else
		- Compromises among groups which differ in interests, ideas, and clout
		- People making stuff up because they need something by a deadline
	- In other words, classes can be typically generated by a human from somewhere in the world, and we shouldn't just blindly trust their class generation process
	- Essentially, even when you have what you are told is a supervised learning problem with labeled data, it can be worth treating it as an unsupervised learning problem
	- If the clusters you find do not match the official classes, then that could be a sign of an unreasonable or irrelevant official scheme, and we would then need to decide whether to trust the official story of our cluster-finding method or not
2. Pattern detection
	- This could include subsetting any pre-determined class
	- This could also include supersetting any unknown class (but maybe expected class)
	- For example, we may want to partition customers into categories, so we can recommend different products to each group
3. Reducing data size
	- We may have features that explain the same information as other features (in terms of our response variable), so we many want to merge those features together through clustering
	- For example, we may try to detect and classify different objects in a 3D point cloud, and thus we may want to focus on geometrically close clusters of points, rather than dealing with overlapping points for every dimension in the dataset

## Properties of Good Clusters
1. Every possible point should belong to one and only one cluster
2. Clusters should be compact
	- Said another way, it would be nice if knowing the cluster could tell us about our features
	- Specifically, we would like to maximize our information value for each cluster
	- A high information value for the clusters means that knowing the cluster reduces our uncertainty about the features
	- Essentially, this means that the points in a cluster should be similar to each other
3. Cluster should be separated
	- This implies that different clusters should have different distributions of features
	- Said another way, if one cluster is much more probable than the other clusters, learning which cluster a point belongs to doesn't reduce uncertainty about its features much
	- Essentially, clusters should be well-separated
4. Clusters should be balanced
	- Balanced clusters imply each cluster is equally probable of being observed
	- Essentially, this means clusters are split fairly evenly amongst each other, but we can't always ensure this
5. Cluster should be parsimonious
	- Essentially, this means we want as few clusters as possible
- Our hope is to find clusters that satisfy these four properties
- Cluster that follow the above properties are known as parsimonious
- Parsimony and balance are fairly simple to measure (i.e. simply using percentages of clusters)
- Measuring compactness and separation depends on having a good measure of distance for our data to start with

## References
- https://www.stat.cmu.edu/~cshalizi/350/2008/lectures/07/lecture-07.pdf
- https://www.quora.com/What-are-some-use-cases-of-clustering-in-machine-learning

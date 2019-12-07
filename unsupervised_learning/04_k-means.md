## General Description
- K-means clustering is a clustering method that assigns each observation to one of k distinct clusters
- Essentially, the goal of k-means clustering is to group similar data points together and discover underlying patterns between them
- The k-means clustering is an unsupervised algorithm, and therefore uses input vectors to make inferences without referring to known (or labelled) output
- The k-means clustering algorithm is one of the simplest and popular unsupervised algorithms
- Essentially, k-means clustering involves defining a k number of clusters (and thus k number of centroids) and associating each data point to a cluster that reduces the cluster sum of squares

## K-Means Algorithm
1. Guess the number of clusters k
2. Guess the means (or centroids) of each cluster
3. Assign each point to the nearest mean
4. Re-compute the mean for each cluster
5a. If the means are unchanged, then exit
5b. Otherwise, return to step 3

## K-Means Objective Function
- As hinted at already, the objective function for the k-means is the sum-of-squares for the clusters
- The sum-of-squares for the clusters is defined as the following:
	- SS = ΣᵨΣᵢ‖xᵢ-mᵨ‖²
		- Where mᵨ is the mean for cluster ϱ
		- Where mᵨ = (1/nᵨ)Σᵢxᵢ
		- Where nᵨ is the number of points in that cluster
- The within-cluster variance for the clusters is defined as the following:
	- Vᵨ = (1/nᵨ)Σᵢ‖xᵢ-mᵨ‖²
		- Where mᵨ is the mean for cluster ϱ
		- Where mᵨ = (1/nᵨ)Σᵢxᵢ
		- Where nᵨ is the number of points in that cluster
- The sum-of-squares for the clusters can also be defined as the following:
	- SS = ΣᵨnᵨVᵨ
- In words, the sum-of-squares is the within-cluster variance multiplied by the cluster size (summed over clusters)
- The sum-of-squares favors compact clusters
- If each cluster is compact, then they will have a small within-cluster variance (so Vᵨ and SS will be small), and thus a small sum-of-squares

## K-Means Search Strategy
- K-means is a local search algorithm
- Therefore, the algorithm makes small changes to the solution that improves the objective
- This sort of search strategy can get stuck in a local minima and may not stop at the best solution
- Local search is also called hill climbing, since it's like a short-sighted climber who tries to get to the top by always going uphill
- If the landscape rises smoothly to a central peak, this will get to that peak
- But if there are local peaks, the climber can get stuck on one
- Therefore, the peak reached by the climber depends on where the climb starts
- In relation to k-means, the different starting positions correspond to different initial guesses about the cluster centers
- Changing those initial guesses will change the output of the algorithm
- Different runs of k-means will generally give different clusters
- Therefore, we should check if points end up clustered together in many different runs

## References
- https://www.stat.cmu.edu/~cshalizi/350/2008/
- https://en.wikipedia.org/wiki/K-means_clustering

## References
- https://www.stat.cmu.edu/~cshalizi/350/2008/
- http://faculty.marshall.usc.edu/gareth-james/ISL/ISLR%20Seventh%20Printing.pdf
- https://en.wikipedia.org/wiki/K-means_clustering

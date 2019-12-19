## General Description
- Principal Component Analysis (PCA) is a method for maximizing the variance of the projected data
- The output of PCA is a set of p orthogonal vectors in the original p-dimensional feature space
- This output of PCA is also referred to as the principal components
- Specifically, PCA is a dimensionality reduction algorithm
- In other words, PCA performs a linear mapping of data from one vector space to a different, lower-dimensional vector space
- Said another way, PCA performs a linear mapping of the data to a lower-dimensional space in such a way that the variance of the data in the low-dimensional representation is maximized
- We use PCA in regression by regressing on the components output by PCA

## The Generalized PCA Algorithm
- First, we need to construct a covariance (or correlation) matrix of the data 
- Then, all of the eigenvalues and eigenvectors are calculated for this matrix
- Then, we can use those eigenvalues to linearly transform the data to a lower dimensional space
- The eigenvectors (i.e. principal components) that correspond to the largest eigenvalues represent the eigenvectors that make up the largest fraction of the variance in the original data
- We can use these components to regress on or to analyze multi-collinearity of our original predictors
- In other words, the dimensionality reduction part of the algorithm is a linear transformation
- However, the algorithm used to calculate eigenvectors is a non-linear transformation

## Definition of the PCA Algorithm 
1. Normalize the data
2. Construct a covariance matrix of the data (which is actually the correlation matrix since it has been normalized)
3. Compute the eigenvectors (and therefore eigenvalues) which diagonalize the covariance matrix
	- V⁻¹CV = D
		- Where C is the covariance matrix
		- Where V is a matrix made up by the eigenvectors that diagonalize the covariance matrix
		- Where V⁻¹ is the inverse of the matrix of eigenvectors
		- Where D is the diagonal matrix of eigenvalues
	- This computation is a non-linear transformation
	- Computing the diagonal matrix of eigenvalues represents a change of basis
4. Use the diagonal matrix of eigenvalues to multiply eigenvectors, which will give us the loadings
	- Loadings are the convariances or correlations between the original variables and the unit-scaled components
	- This computation is a linear transformation

## Use-Cases of PCA
- If we want to determine which features are correlated with each other, then we can use principal components to interpret the weighted combinations of the original features
- If we want to determine how correlated each feature is correlated with each other, then we can use principal components to interpret the weighted combinations of the original features
- If we want to determine the fraction of variance that a related combination of original features captures in the data, then we can determine the fraction λᵢ of the variance that the ith component captures in the original data
	- Where λ represents an eigenvalue
- If we want to determine the related combination of original features that captures the greatest fraction of variance in the data, then we can determine the ith component that captures the greatest fraction λᵢ of the variance in the original data

## How Eigenvectors relate to PCA
- As stated previously, PCA finds the eigenvector that maximizes the variance
- The eigenvector that maximizes the variance is the same eigenvector that minimizes the error (between the data and the eigenvector)
- Therefore, PCA will find the eigenvector that maximizes the variance by finding the eigenvector that minimizes the variance

## Interpreting the Principal Components
- Principal components are ordered based on how much variance they make up in the data
- The first principal component has the following properties:
	- The first principal component is the eigenvector of the covariance matrix that makes up the most variance
- The second principal component has the following properties:
	- The second principal component is the eigenvector orthogonal to the first component
	- The second principal component is the eigenvector that makes up the second most variance
- The third principal component has the following properties:
	- The third principal component is the eigenvector orthogonal to the first and second components
	- The third principal component is the eigenvector that makes up the third most variance
- Projections on to all principal components are all completely uncorrelated with each other

## References
- https://www.stat.cmu.edu/~cshalizi/350/2008/lectures/10/lecture-10.pdf
- https://www.stat.cmu.edu/~cshalizi/uADA/12/lectures/ch18.pdf
- https://math.stackexchange.com/questions/23596/why-is-the-eigenvector-of-a-covariance-matrix-equal-to-a-principal-component
- https://stats.stackexchange.com/questions/2691/making-sense-of-principal-component-analysis-eigenvectors-eigenvalues
- https://stats.stackexchange.com/questions/143905/loadings-vs-eigenvectors-in-pca-when-to-use-one-or-another
- https://en.wikipedia.org/wiki/Principal_component_analysis
- https://en.wikipedia.org/wiki/Dimensionality_reduction#Principal_component_analysis_(PCA)
- https://stats.stackexchange.com/questions/290750/linearity-of-pca
- https://shankarmsy.github.io/posts/pca-vs-lr.html

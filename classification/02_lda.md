## Assumptions
- Observations within each class are drawn from a multivariate Gaussian distribution
- Each class has its own mean vector, but the same covariance matrix for each classification

## Preparing for LDA
- Check assumptions
	- Gaussian distribution - Use log and root transformations to ensure Gaussian distributions are maintained
	- Same variance - standarize data to ensure equal variance is maintained across distribution
- Possibly remove outliers

## Why do we need this method
- When the classifications are well-separated, the parameter estimates for the logistic model are suprisingly unstable, and LDA does not suffer from this
- If n is small and the distributun of the predictors is approximately normal in each of the classifications, the LDA model is more stable than the logistic model
- For the above reasons, and many other reasons, LDA is the preferred method when dealing with >2 response classifications

## Difference between Logistic Regression and LDA
- Logistic Regression involves directly modeling Pr(Y=k|X=x) using the logistic function
	- Estimates parameters using maximum likelihood
- LDA involves direcetly modeling Pr(Y=k|X=x) using Bayes Theorem
	- Estimates parameters using maximum likelihood

## Difference between PCA and LDA
- PCA is an unsupervised learning method that inolves linear transformations (dimensionality reduction) to find the features that make up the most variability
- LDA is a supervised learning method that involves linear transformations (dimensionality reduction) to maximize the distance between classes and minimize the distance within classes

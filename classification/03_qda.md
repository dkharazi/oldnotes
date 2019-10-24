## Assumptions
- Observations within each class are drawn from a multivariate Gaussian distribution
- Each class has its own mean vector and the same convariance matrix and a different covariance matrix for each classification as well

## Approach
- Make predictions using Bayes theorem

## Who do we need this method?
- QDA holds the same assumptions as LDA except that the covariance matrix is not common for each classification
- Pros
	- Typically more accurate and more flexible due to ability to account for non-linear relationships, and more quadratic relationships between predictors
- Cons
	- Computationally expensive
	- More room for overfitting

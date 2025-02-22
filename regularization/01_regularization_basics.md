## General Description
- Regularization is a variable selection technique used in regression, roughly speaking
- We typically use regularization when when we have a large amount of variables in our model (and a smaller amount of data), since this type of model typically leads to overfitting
- Regularization will significantly reduce the variance of the model without substantially increasing the bias
- In other words, regularization is commonly used to avoid overfitting
- To achieve this, regularization methods involve shrinking OLS coefficients, where only the most significant coefficients remain (as we increase the tuning parameter to the most optimal value)
- Essentially, regularization coefficients are just OLS coefficients with an added penalty

## Steps in General Regularization
1. Standardize data
	- Centering the variables will means there is no longer an intercept
	- This is useful because the intercept will not be much of a factor in any shrinkage
2. Minimize the objective function (i.e. OLS objective function) including an added penalty to the OLS coefficients, in order to find the most significant coefficients

## References
- http://www.socr.umich.edu/people/dinov/courses/DSPA_notes/17_RegularizedLinModel_KnockoffFilter.html
- https://stats.stackexchange.com/questions/4961/what-is-regularization-in-plain-english
- https://towardsdatascience.com/regularization-in-machine-learning-76441ddcf99a
- https://en.wikipedia.org/wiki/Regularization_(mathematics)
- http://laid.delanover.com/difference-between-l1-and-l2-regularization-implementation-and-visualization-in-tensorflow/
- https://www.quora.com/What-is-the-difference-between-L1-and-L2-regularization-How-does-it-solve-the-problem-of-overfitting-Which-regularizer-to-use-and-when
- https://stats.stackexchange.com/questions/86434/is-standardisation-before-lasso-really-necessary

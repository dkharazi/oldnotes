## General Description
- An estimator represents a guess of a population parameter
- A statistic is an estimator of some population parameter
- A point estimate is a statistic using sample data
- Roughly, a point estimate represents a guess of a population parameter using sample data
- A point estimate assumes the distribution associated with the data follows a certain form
- As mentioned previously, a point estimate is a statistic (and thus an estimator)
- We call it a point estimate because it only returns a single value for the parameter
	- Other types of estimates will return ranges

## Bias and Variance
- The bias of an estimator is the expected error in its estimate (θhat-θ)
- An estimator is unbiased if its bias is zero
- An estimator is consistent if it converges to the true parameter value as the sample size goes off to infinity
- A consistent estimator is not necessarily unbiased
	- For example, the sample variance is a consistent estimator of the population variance, but it has a negative bais (and therefore is biased)
- Our goal is to find an estimator that is unbiased with a very small variance
- An efficient statistic for a parameter is one that is unbiased and has a minimum variance
- A sufficient statistic for a parameter is one where the distribution of samples, conditional on the statistic, is independent of the parameter
- Every efficient estimator is a sufficient statistic for its parameter

## Common Types of Estimates
- Least Squares
	- It is very common to measure errors by the square of the difference between what is predicted by a hypothesis and what is actually measured
- Maximum Likelihood
	- The likelihood of getting our data is simply the probability of seeing all those values of data conditional on a certain value of the parameter
	- Taking the data as fixed, we ask what value of the parameter maximizes the likelihood
	- The maximum-likelihood value of θ is the one which makes our data as probable as possible, but it is not the most probable value of the parameter given our data

## Confidence Regions
- One of the problems with point estimates is that they give us a single value
- This may be the best single guess we could come up with for the value of the parameter, but it would be nice if we could get some idea of the range of good values (i.e. the range of what's reasonable given our data)
- This is accomplished through confidence intervals (or confidence regions)
- The process of constructing a confidence interval follows this pattern:
	1. We choose a statistic X
	2. We pick a probability α representing the change of being wrong
	3. For each value of the parameter θ,  we calculate an interval such that P(X∈C(θ))=α
- Generally, we choose an interval that is symmetric about our statistic
- Roughly, the meaning of the confidence region is "either the real parameter is in here, or we're very unlucky"
- Said another way, it becomes plausible that there is generally a trade-off between getting a tight estimate having a small confidence region, and convering our asses
- We generally refer to confidence intervals when θ is one-dimensional, and confidence regions when θ is more general (i.e. multi-dimensional)

## References
- http://bactra.org/prob-notes/srl.pdf

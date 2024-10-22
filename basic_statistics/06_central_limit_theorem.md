## General Description
- The central limit theorem states that any distribution of enough sample means will follow a normal distribution, assuming a large sample size for each sample mean

## Importance of CLT according to Shalizi
- The CLT tells us that, if only we can arrange to be dealing with IID sequences, in the long run we know what the distributions must be
- Even better, it's always the same distribution
- Still better, it's one which is remarkably easy to deal with, and for which we have a huge amount of theory
- Essentially, we can manipulate our problem so that the CLT applies, and (at least asymptotically), we will have it made

## Ways the CLT can Fail
- The random variables may not be independent
	- Still, there are some situations in which this can be overcome
- The random variables may not have well-defined variances
	- There are quite respectable probability distributions with a well-defined mean, but where the integral for the variance diverges
	- As we know, if there is not a well-defined variance for a probability distribution, the sequence of its random variables will not have equal variance
	- And, equal variance is an assumption of the central limit theorem
- The variables might not be identically-distributed
	- There are some generalizations here, too, supposing at least that the means are identical

## Why Things are Gaussian
- Typically, errors in measurements are roughly Gaussian
- Assuming that the causes of the errors for some random variable are statistically independent, then the errors will typically have a mean of 0 (i.e. no systematic bias is introduced)
- We should expect the sum of the errors (i.e. total error) to have a Gaussian distribution
- And, the random variable will fit closer and closer to a Gaussian distribution as errors with more independent causes are added
- In general, whenever we have marginal, additive effects of many independent causes, we are inclined to expect a Gaussian distribution

## References
- http://bactra.org/prob-notes/srl.pdf

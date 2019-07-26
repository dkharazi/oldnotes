## Expectation
- The expected value of a random variable is a population parameter, which is also a random variable
- The expected value of an unbiased estimator is the population parameter
- Although the expected value refers to a random variable (which is a function), it can sometimes (incorrectly) be referred to as the output of some random function [i.e. f(x)] once a sample has been realized
	- Where f is typically a parameter (which is a random variable)
	- And x is a sample (i.e. data)
- A correct way of calculating the output of some parameter could be written as: mu(x) instead of E[X]

## Prediction
- Since we don’t feel comfortable with the word “guess”, we call it a “prediction” instead
- The best one-number guess we could make for a random variable is just its expected value
- The typical process of finding the best prediction for some random variable is as follows:
	1. In order to find the best prediction for some random variable, we need to find its expected value
	2. A random variable's expected value will equal some population parameter, which is almost always unknown
		- Therefore, we will need to use the (maximum likelihood) estimator of the population parameter 
	3. The estimator is equal to some sample statistic, so we then calculate the sample statistic that is the maximum likelihood estimator

## Parameter
- In the frequentist sense, a parameter is a fixed value
- In the bayesian sense, a parameter is a random variable

## Statistic
- A statistic refers to a function of the data (or sample)
- Mathematically, a statistic refers to a function that maps the sample space to a set of point estimates
- Example: X-bar	
- A statistic is a random variable
	- It inherits its distribution from that of its random variable
	- Example: X-bar
		- X-bar inherits the distribution of its random variable X
		- This is because X-bar is a function of the data, which are typically considered to be random variables

## Estimators
- An estimator refers to a function of the data (or sample) that attempts to estimate a population parameter
	- In other words, an estimator is a statistic that is an estimate of a population parameter
		- With that being said, all estimators are statistics, but not all statistics are estimators
- Mathematically, an estimator refers to a function that maps the sample space to a set of point estimates
	- The input is the sample space
	- The output is a point estimate
	- As your sample size grows larger and larger, an estimator is thought to converge to the population parameter
- An estimator is a random variable for the same reason that a statistic is a random variable
	- Therefore, it has a distribution inherited from its original random variable (i.e. X), similar to a statistic
	- The expected value of 
- Example: mu-hat is an estimator of mu
- Example: X-bar is an estimator of mu if X is normally distributed
- An estimator is consistent if it converges to the population parameter as the sample size grows
- An estimator is unbiased if its bias is zero 

## Point Estimate
- A point estimator is another name for an estimator
	- In other words, a point estimator is a random variable
- A point estimate refers to the actual data value associated with an estimator or statistic
	- In other words, a point estimate is some constant (or fixed value)
- Mathematically, a point estimate refers to the output of an estimator
- Example: Given x-bar=5, we can say that x-bar is a statistic and 5 is the point estimate
- This term is used somewhat loosely: sometimes people use point estimates and estimators interchangeably

## References
- https://stats.stackexchange.com/questions/26396/expectation-of-an-estimator
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- https://stats.stackexchange.com/questions/47728/what-is-the-difference-between-an-estimator-and-a-statistic
- https://en.wikipedia.org/wiki/Point_estimation
- https://en.wikipedia.org/wiki/Estimator
- https://stats.stackexchange.com/questions/135960/difference-between-bias-and-error

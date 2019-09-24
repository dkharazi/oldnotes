## Basic Background
- Continuous random variables have a probability density function (also known as a likelihood function)
- Probability density functions take in sample data as input and return likelihoods as output
- Likelihoods represent the chance (or the joint probability) of observing the data given the parameters, assuming the data is represented by the distribution we chose

## General Description
- Maximum likelihood estimation is a method that determines values for the parameters of a model
- The parameter values are found such that they maximize the likelihood that the process (or random variable) described by the model produced the data that were actually observed
- The optimal parameters that maximize the likelihood are called the maximum likelihood estimates
- MLE can be seen as a special case of the MAP estimation, where we assume the parameters have a prior that is uniformly distributed

## More Specific Definition
- Technically speaking, maximum likelihood estimation is a method of estimating the parameters of a distribution by finding the parameter values that maximize the likelihood of observing the data given our parameters
- Said another way, maximum likelihood estimation involves finding the value of the parameter that gives us the mode of our sample data
- Said another way, our maximum likelihood estimate is the parameter that gives us the mode

## Motivating the Algorithm
- First, we have some data
- Then, we may have a general idea of what distributional family the data belongs to
- Now, we want to know which curve was most likely responsible for creating the data points that we observed
	- For example, we have sample data and we believe that our sample data is normally distributed
	- So, we would want to know how exactly that normal distribution looks in terms of our data
	- This means we are interested in how the parameters should be adjusted to find the exact normal curve that has given us  our sample data
- We use maximum likelihood estimation to find the values of our parameters, which will reults in the curve that best fits the data
- Each parameter typically has a corresponding formula that provides us with the MLE

## General Algorithm
1. Find the probability density function that seems to fit our data
2. Take the log of the likehood function (or the p.d.f)
3. Take the partial derivative of the function with respect to each parameter

## Does MLE Always Work
- No, since random variables from the real world take on more complicated functions, rather than the standard probability density functions (i.e. normal distribution) we're used to seeing
- In other words, the derivative of the log-likehood function does not usually lead us to a straight-forward formula
	- i.e. it's way too hard/impossible to differentiate the function by hand
- Therefore, iterative methods, such as Expectation-Maximization algorithms or Gradient Descent, are used to find numerical solutions for the parameter estimates.

## Why Likelihoods Aren't Probabilities
- This is mostly just statisticians being pedantic
- Most people tend to use probability and likelihood interchangeably, but statsticians distinguish between the two (for good reason)
- Probabilities are used to describe the chance associated with discrete random variables

## References
- https://towardsdatascience.com/a-gentle-introduction-to-maximum-likelihood-estimation-9fbff27ea12f
- https://www.youtube.com/watch?v=XepXtl9YKwc

## Introduction to Errors
- An error is the difference between an observed value and its population parameter
	- The population parameter is typically fixed and unobserved
		- For example, we usually don't know the population mean in research
		- But sometimes in very general cases, we do in fact know the the population mean, such as the mean height in a population of 21-year-old men
		- Thus, errors are almost always theoretical and unobservable
- A residual is the difference between an observed and its estimated value
        - Residuals are estimates of the true errors
        - Residuals are empirical and observable
- For example: the sample mean could serve as a good estimator of the population mean
	- The difference between each observation in our sample and the unobservable population mean is a statistical error
		- xi - mu
	- The difference between each observation in our sample and the observable sample mean is a residual
		- xi - x-bar
- Essentially, we are able to estimate error associated with a population parameter by first estimating the population parameter itself, which will allow us to estimate a given quantity based on our observed data, which will effectively allow us to work with residuals
	- Mathematically, (xi - theta) becomes (xi - theta-hat) or (xi - x-bar) (using the sample mean as our estimator of the population mean)
	- (xi - x-bar) is the equation of a residual

## Sampling Error
- In plain English, the sampling error refers to error caused by observing a sample instead of the entire population
- Sampling error is a property of an estimator
- The sampling error is influenced by our sample size

## Standard Error
- The standard error is the standard deviation of the outcomes of an estimator
	- In other words, the standard error is used to quantify the amount of uncertainty around our point estimate
- Mathematically, the standard error is the square root of the variance
- The standard error is a property of an estimator
- The standard error is influenced by our sample size and the standard deviation of our random variable

## Bias-Variance Tradeoff
- Error is a property of a random variable
	- Bias and variance typically refer to the errors associated with an estimator, which is a random variable
		- An estimator is unbiased if the expected value of the error term is 0
			- We will never know the errors, so we use the residuals to estimate the errors
			- Biasedness obviously relates to bias in the bias-variance tradeoff concept, since an unbiased estimator can be a good indication that we will receive a low training error in the bias-variance tradeoff
			- Residuals are mathematically defined as ei = yi − (β-hat0 + β-hat1*xi)
                        - Residuals can be considered estimates of the errors	
- An estimator is consistent if our parameter estimate converges to the true parameter as n → ∞
			- Consistency relates to variance in the bias-variance tradeoff concept, since a consistent estimator can be a good indication that we will receive a low variance in the bias-variance tradeoff
	- Whereas irreducible error typically refers to the error provided by a (population) random variable
1. Bias
	- Bias of an estimator is associated with training error
	- High training error/bias leads to underfitting
	- Bias is caused by systematic or statistical errors
	- Specifically, sources of bias are:
		- A lack of training data (sampling error of the training set)
		- Too few features in our training data
		- Flaws in the model
			- Example: we may need to train the data on a more complicated model or an entirely different model altogether
		- Flaws in the modeling process
			- Example: we may not be using the proper equations correctly
			- Example: we may need to decrease regularization
			- Example: misunderstanding of bayesian modeling algorithms and hyper-parameter fitting
		- Flaws in the measurement instrument
		- Flaws in the measurement process
		- Flaws in determing the best way to measure some variable of interest
			- Example: we may correctly measure some imperfect proxy for what we're really interested in, but will still receive poor accuracies, since we are measuring an imperfect proxy to begin with
2. Variance
	- Variance of an estimator is associated with testing/cross-validation error
	- High testing error/variance leads to overfitting
	- Variance is caused by overall sampling error or mistaking noise for signal during the training portion of our modeling process
	- Specifically, sources of variance are:
		- A lack of testing/overall data (overall sampling error)
		- Too many features in our training data
		- Flaws in the model
			- Example: we may need to train the data on a less complicated model or an entirely different model altogether
		- Flaws in the modeling process
			- Example: we may need to increase regularization
3. Irreducible Error
	- Inherent randomness caused by natural variability in the population parameter
                - This natural variability is a result of not knowing every variable and its true relationship with all of the other random variables in the world
        - A certain level of irreducible error will always exist, and is even incorporated in (population) random variables
	- Random error (or noise) is thought of as a random variable itself, with a mean of 0
	- The error term is mathematically defined as εi = Yi − (β0 + β1*xi)
		- The error term is also known as the random error, noise, or ε
	- Irreducible error represents the standard deviation of the random error term (ε)
		- It wouldn't make any sense for the irreducible error to be the error term, since the irreducible error is a fixed number representing uncertainty, rather than a random variable, which is a function




## References
- https://www.learnopencv.com/bias-variance-tradeoff-in-machine-learning/
- https://en.wikipedia.org/wiki/Errors_and_residuals
- https://en.wikipedia.org/wiki/Sampling_error
- https://en.wikipedia.org/wiki/Observational_error#Random_errors_versus_systematic_errors
- https://newonlinecourses.science.psu.edu/stat509/node/27/
- https://www.physics.umd.edu/courses/Phys276/Hill/Information/Notes/ErrorAnalysis.html
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- https://stats.stackexchange.com/questions/133389/what-is-the-difference-between-errors-and-residuals
- http://scott.fortmann-roe.com/docs/BiasVariance.html

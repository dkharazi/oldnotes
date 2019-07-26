## Errors and Residuals
- Statistical error is referred to as error for short
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
- Essentially, we are able to estimate statistical error by estimating the populion parameter
	- Mathematically, (xi - theta) becomes (xi - theta-hat) or (xi - x-bar) (using the sample mean as our estimator of the population mean)
	- (xi - x-bar) is the equation of a residual

## Measurement error
- Measurement error represents 
- There are two types of measurement error:
	1. Systematic error
	2. Statistical error
- Examples of measurement error
	- Flaws in the measurement instrument
	- Flaws in the measurement process
	- Flaws in determining the best way to measure some variable of interest
		- We correctly measure some imperfect proxy for what we're really interested in





## Bias-Variance Tradeoff
- Noise is made up of the following:
	1. Bias
		- Refers to errors associated with parameters, whereas residuals refer to errors associated with observations
		- Thought of as systematic errors
		- Relates to accuracy (getting output close to the true value/parameter)
		- Source of bias is typically related to:
			- Flaws in the measurement instrument
			- Flaws in the measurement process
			- Flaws in the model
			- Flaws in the modeling process
			- Flaws in determing the best way to measure some variable of interest
				- We correctly measure some imperfect proxy for what we're really interested in
	2. Variance
		- Refers to errors in the context of parameters (or sometimes other more general random variables)
		- Thought of as random errors
		- Relates to precision (getting consistent output)
		- Source of variance is typically sampling error
	3. Irreducible error
		- Refers to errors associated 


## Bias-Variance Tradeoff - Corrected
- An estimator is unbiased if ...
- An estimator is consistent if ...
- ... is made up of the following
	1. Bias
	2. Variance
	3. Irreducible error
		- Refers to the standard deviation of the error term
			- The error term is mathematically defined as εi = Yi − (β0 + β1*xi)
			- The error term is also known as the random error, noise, or ε
			- Residuals are mathematically defined as ei = yi − (β-hat0 + β-hat1*xi)
			- Residuals can be considered to be estimates of the errors




## Fluctuations in the random variable Y

## Sampling error
- to do

## Random Error (or noise)
- Errors represent the uncertainty 
- Random error represents:
	- Measurement error, which represents:
		- Statistical error
		- Systematic error
			- Refers to bias of predictions
	- Fluctuations (in the random variable Y)
	- Sampling error
		- Error caused by having a small sample size
		- Naturally occurring errors that are expected from sampling a random variable


- Random error represents measurement error, or fluctuations in the random variable Y, or some combination of both
- Standard error is a measure of random error
- Standard error is used to quantify the amount of uncertainty there is around our point estimate
- Random error refers to the amount of uncertainty there is around our point estimate



## Bias
- The bias of an estimator
- If variables from the random sample do not have similar dependencies as the variables from the population of interest, then there may be some level of systematic error or bias that has been introduced to the experiment
        - Meaning, the sample shouldn't have any absence or presence of other dependencies with respect to the population variables of interest with a large enough sample size
        - In other words, if there are any dependencies between variables for the population, there should be similar dependencies between those same variables for any sample with a large sample size

## Two Types of Errors
1. Random Errors (or random noise)
	- A random variable's true standard deviation is a measure of random errors
	- Unpredictable; otherwise we would have a deterministic system

2. Systematic Errors
	- Refers to bias
	- Bias is mathematically defined as the difference between the sample mean and the population parameter
	- An estimator is unbiased if its bias is 0

## Types of Systematic Errors (or Bias)
1. Sampling Error
	- Mathematically, sampling error is defined as the difference between a sample statistic (used to estimate a population parameter) and the actual (but unknown) value of the population parameter
		- Obviously, this is nearly impossible to calculate in most cases, since the population parameter is almost always unknown
	- In plain English, the sampling error refers to error caused by observing a sample instead of the entire population
		- This is influenced by the sample size and the random variable's standard deviation 
	- Standard error is a measure of sampling error

## References
- https://en.wikipedia.org/wiki/Errors_and_residuals
- https://en.wikipedia.org/wiki/Sampling_error
- https://en.wikipedia.org/wiki/Observational_error#Random_errors_versus_systematic_errors
- https://newonlinecourses.science.psu.edu/stat509/node/27/
- https://www.physics.umd.edu/courses/Phys276/Hill/Information/Notes/ErrorAnalysis.html
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- https://stats.stackexchange.com/questions/133389/what-is-the-difference-between-errors-and-residuals
- http://scott.fortmann-roe.com/docs/BiasVariance.html

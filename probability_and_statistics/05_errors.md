## Introduction to Errors
- An error is the difference between a population parameter and its observed value
	- The population parameter is typically fixed and unobserved
		- For example, we usually don't know the population mean in research
		- But sometimes in very general cases, we do in fact know the the population mean, such as the mean height in a population of 21-year-old men
		- Thus, errors are almost always theoretical and unobservable
- A residual is the difference between an estimated parameter and its observed value
        - Residuals are estimates of the true errors
        - Residuals are empirical and observable
- For example: the sample mean could serve as a good estimator of the population mean
	- The difference between each observation in our sample and the unobservable population mean is a statistical error
		- xi - mu
	- The difference between each observation in our sample and the observable sample mean is a residual
		- xi - x-bar
		- Also can be defined as ei = yi − (β-hat0 + β-hat1*xi)
- Essentially, we are able to estimate error associated with a population parameter by first estimating the population parameter itself using our observed data, which will effictively lead us to working with residuals
	- Mathematically, (xi - theta) becomes (xi - theta-hat) or (xi - x-bar) (using the sample mean as our estimator of the population mean)
	- (xi - x-bar) is the equation of a residual

## Sampling Error
- In plain English, the sampling error refers to error (in our estimates) caused by observing a sample instead of the entire population
- Sampling error is a property of an estimator
- The sampling error is influenced by our sample size and sample standard deviation
	- The more data we receive, the smaller our errors become
	- Said another way, as our errors become smaller, the impact of estimating the errors using residuals becomes extremely marginal

## Standard Error
- The standard error is a measure of sampling error
	- More specifically, the standard error is used to quantify the amount of uncertainty around our point estimate
	- Mathematically, the standard error is the standard deviation of the outcomes of an estimator
- The standard error is a property of an estimator
- The accuracy of our estimates depends on our sample standard deviation and our sample size, and our sample standard deviation is typically considered to be fixed while our sample size can change easily
	- If our sample size is decently large, then our sample standard deviation has some effect on our estimates
	- If our sample size is infinitely large, then our sample standard deviation doesn't really have an effect on our estimates 

## Source of Inaccuracies in Estimates
- Sampling error is one source of inaccurate estimates
- Bias can be a greater source of inaccurate estimates

## References
- https://en.wikipedia.org/wiki/Errors_and_residuals
- https://en.wikipedia.org/wiki/Sampling_error
- https://en.wikipedia.org/wiki/Observational_error#Random_errors_versus_systematic_errors
- https://newonlinecourses.science.psu.edu/stat509/node/27/
- https://www.physics.umd.edu/courses/Phys276/Hill/Information/Notes/ErrorAnalysis.html
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- https://stats.stackexchange.com/questions/133389/what-is-the-difference-between-errors-and-residuals

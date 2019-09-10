## Overview of Confidence Intervals
- Confidence intervals are a frequentist concept
	- As a reminder, frequentists believe that the data is random and undetermined, and the population parameters are fixed and have already been determined before we even started gathering samples
- Therefore, a frequentist defines a 95% confidence interval as an interval that contains the population parameter 95% of the time
	- In other words, if we took 100 random samples of a population and construct 100 different 95% confidence intervals, then 95 of the 100 intervals will contain the population parameter
	- The interval we just constructed is either in the 95% that do contain the interval, or the 5% that don't contain the interval
	- The event is binary - it either is or is not in the interval - it's either a 0% or 100% of our population parameter being contained in the interval
- Example: A game of ring toss aiming for a peg
	- The tossed ring is our confidence interval, and the peg is our population parameter
	- Confidence intervals are like the ring after it has been thrown at the peg
	- The peg is either within the ring or not

## Formula for Confidence Intervals
- The confidence interval involves the following metrics:
	- Standard Error: represents sampling error while accounting for the variable's standard deviation
	- Margin of error:represents standard error with some additional room for error
- When defining a confidence interval for a population parameter, we could write it as the following:
	- sample-parameter ± Margin of Error
- Example: Define a 95% confidence interval for the population mean
	- x-bar ± Margin of Error
	- Where the margin of error = 1.96 * standard-error

## Overview of Credible Intervals
- Credible intervals are a bayesian concept
	- As a reminder, bayesians believe that the data is fixed and determined, and the population parameters are random and undetermined
- Therefore, a bayesian defines a 95% credible interval as an interval with a 95% of containing the population parameter
	- In other words, if we took 100 random samples of a population, then we can construct a single (credible) interval from the samples and say there is a 95% chance that the population parameter is within the interval
- Example: A game of ring toss aiming for a peg
	- The tossed ring is our credible interval, and the peg is our population parameter
	- Credible intervals are like the ring before it has been thrown at the peg
	- There is a % chance that the ring will land around the peg

## Final Notes about the Two Intervals
- Confidence intervals and credible intervals arrive at the same answer, but use different approaches
- Confidence intervals essentially measure the standard error of some population parameter by sampling confidence intervals
- Credible intervals essentially measure the standard error of some population parameter by looking at the range (or interval) after taking 95% of the data from the sampling distribution
- Although probabilities from frequentist inference is based on long-run frequencies, probabilities from bayesian inference is based on long-run frequencies as well
- The difference comes from a different way of thinking, and thus the reason for the inclusion of priors in bayesian inferences
- Therefore, probabilities within bayesian and frequentist inference should eventually converge to the same estimates if the prior is uninformative within the example of  bayesian inference

## References
- https://www.reddit.com/r/statistics/comments/1kbcl8/eli5_95_confidence_intervals/
- https://stats.stackexchange.com/questions/22/bayesian-and-frequentist-reasoning-in-plain-english
